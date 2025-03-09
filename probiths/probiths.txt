# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Horseshoe shrinkage prior in Bayesian Probit regression Use probiths (horseshoenlm) With (In) R Software
install.packages("horseshoenlm")
install.packages("pgdraw")
library("horseshoenlm")
probiths = read.csv("https://raw.githubusercontent.com/timbulwidodostp/probiths/main/probiths/probiths.csv",sep = ";")
# Estimation Horseshoe shrinkage prior in Bayesian Probit regression Use probiths (horseshoenlm) With (In) R Software
z <- probiths$z
X <- cbind(probiths$X1, probiths$X2, probiths$X3)
burnin <- 100
nmc    <- 500
ntrain <- 100
ntrain <- 250
ntest  <- 100
n <- ntest + ntrain
ztrain <- z[1:ntrain]
Xtrain  <- X[1:ntrain, ]
ztest <- z[(ntrain + 1):n]
Xtest  <- X[(ntrain + 1):n, ]
probiths <- probiths(z = ztrain, X = Xtrain, method.tau = "halfCauchy", burn = burnin, nmc = nmc, thin = 1, Xtest = Xtest)
BetaHat <- probiths$BetaHat
BetaHat
DIC <- probiths$DIC
DIC
WAIC <- probiths$WAIC
WAIC
# Horseshoe shrinkage prior in Bayesian Probit regression Use probiths (horseshoenlm) With (In) R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished