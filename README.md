# Aproximação de pontos por função linear e quadrática R
Aproximação de pontos por funções lineares e quadráticas pelo R

# Aproximação Linear
## Obentdo os dados e fazendo uma visualização dos mesmos
```R
pesos44=read.csv("G:/pesos44.txt", sep = ";")
plot(pesos44)
```
## Gerando a função linear
```R
a=length(pesos44[,1])
b=sum(pesos44[,1])
c=sum(pesos44[,1])
d=sum((pesos44[,1])^2)
matrix=matrix(c(1,2,3,4),ncol=2) 
matrix[1,1]=a;matrix[2,1]=b;matrix[1,2]=c;matrix[2,2]=d #matrix
vector=c(sum(pesos44[,2]),sum(pesos44[,1]*pesos44[,2])) #vector
matrix
vector
#solve(matrix,vector) #função que resolve o sistema matricial
# -60.06608  70.33368
```
## Plotando os pontos com a função
```R
plot(pesos44)#gráfico  + reta
x_ajuste <- seq(min(pesos44[,1]), max(pesos44[,1]), by=0.01)
y_ajuste <--60.06608  +70.33368*(x_ajuste)
points(x_ajuste, y_ajuste, type="l",col="red",lwd = 3)
```

# Aproximação Quadrática
## Obentdo os dados e fazendo uma visualização dos mesmos
```R
barco2=read.csv("G:/barco2.txt", sep = ";")
plot(barco2)
```
## Gerando a função quadrática
```R
n=3 ;M=matrix(nrow=n,ncol=n)  #numero de graus da linha (n-1)
for(k in 1:n){
  for(j in 1:n){
    M[k,j]= sum(barco2[,1]^((k-1)+(j-1))) } } #matrix
M[1,1]=39;V=0
for(i in 1:n){
  V[i]=sum(barco2[,2]*barco2[,1]^(i-1)) } #vector
M#matrix
V#vector
#solve(M,V) #função que resolve o sistema matricial
#376.517810 -75.988612   3.869957
```
## Plotando os pontos com a função
```R
plot(barco2) #gráfico  + "reta" 
x_ajuste <- seq(min(barco2[,1]), max(barco2[,1]), by=0.01)
y_ajuste <- 376.517810 -75.988612*(x_ajuste)   +3.869957*(x_ajuste)^2
points(x_ajuste, y_ajuste, type="l",col="red",lwd = 3)
```
