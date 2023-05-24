# BD-P3-CASO-1
1*) π Nom,Zona,Edad PERS
2*) π Zona PERS
3*) π Zona CLUB
4*) π Zona PERS ∪ π Zona CLUB
5*) alternativa 1*) π Nomc (σ Zona='Capital' ∨ Zona='Desamparados' ∨ Zona='Rivadavia' CLUB)
    alternativa 2*) π Nomc ((σ Zona='Capital' CLUB) ∪ (σ Zona='Desamparados' CLUB) ∪ (σ Zona='Rivadavia' CLUB))
6*) π Nom,Dni,Edad (PRAC⨝PERS)
7*) alternativa 1*) π Dni (PRAC⨝(σ Nomd='Tenis' DEPO))
    alternativa 2*) CD= π Codd σ Nomd='Tenis' DEPO
                    π Dni (PRAC⨝CD)
    alternativa 3*) π Dni (σ Nomd='Tenis' (DEPO⨝PRAC))
8*) alternativa 1*) π Nomc (PRAC⨝CLUB⨝(σ Nomd ='Fútbol' DEPO))
    alternativa 2*) CD= π Codd σ Nomd='Fútbol' DEPO
                    π Nomc (PRAC⨝CLUB⨝CD)
    alternativa 3*) π Nomc (σ Nomd ='Fútbol' (PRAC⨝CLUB⨝DEPO))
9*) CC= π Codc,Nomc CLUB
    π Dni, Nom, Nomd, Nomc (PRAC⨝PERS⨝DEPO⨝CC)    
10*) COD1= σ Codd='D01' PRAC
     COD2= σ Codd='D22' PRAC
     COD3= σ Codd='D10' PRAC
     π Dni,Nom ((COD1 ∩ COD2 ∩ COD3) ⨝ PERS)
11*) A= PRAC ⨝ (π Codc σ Nomc='Ausonia' CLUB)
     π Dni, Nom ((PRAC - A) ⨝ PERS)
12*) alternativa 1*) A= π Codc σ Nomc='Ausonia' CLUB
                     B= π Codc σ Nomc='UVT' CLUB
                     π Dni ((A ⨝ PRAC)∪(B ⨝ PRAC))
     alternativa 2*) π Dni (π Codc (σ Nomc ='Ausonia' ∨ Nomc ='UVT' CLUB) ⨝ PRAC)
13*) A= π Codd (PRAC ⨝ (π Dni σ Sexo='F' PERS))
     B= π Codd (PRAC ⨝ (π Dni σ Sexo='M' PERS))
     B-A
14*) JuanP=ρJuanP(π Zona σ Dni= 20498425 PERS)
     π Dni,Nom,Dir (JuanP ⨝ JuanP.Zona = PERS.Zona PERS)     
15*) AnaG= ρAG(πEdad σ Dni=18498425 PERS)
     π Dni,Nom (AnaG ⨝ AG.Edad < PERS.Edad PERS)
     o tambien*) AnaG= ρAnaG(πEdad σ Dni=18498425 PERS)
                 π Dni,Nom (AnaG ⨝ AnaG.Edad < PERS.Edad PERS)
16*) PersP=π Dni,Nom,Zona PERS
     ZonaP=π Codc,Zona CLUB
     π Dni,Nom (PersP ⨝ PRAC ⨝ ZonaP)
17*)      
18*) alternativa 1*) π Nomd ((π Codd,Codc PRAC ÷ π Codc CLUB) ⨝ DEPO)
     alternativa 2*) A= π Codc CLUB
                     π Nomd ((π Codd,Codc PRAC ÷ A) ⨝ DEPO)
19*) A=π Codd(σ Clase='Balón' DEPO)
     π Codc,Codd PRAC ÷ A
20*) alternativa 1*) (π Dni,Codd PRAC ÷ π Codd DEPO) ⨝ PERS
     alternativa 2*) A=π Codd DEPO
                     (π Dni,Codd PRAC ÷ A) ⨝ PERS
21*) A= π Codc σ Nomc='Banco Hispano' CLUB
     π Nom ((π Dni,Codd PRAC ÷ (π Codd,Codc PRAC ÷ A)) ⨝ PERS)                     
