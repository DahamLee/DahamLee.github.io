## Derivatives2

### Markov Process
	- E(S_T|S_t) = E(S_T|S_t, S_t-1, S_t-2..)
	- in here S_t-1, S_t-2... are useless

1. EMH (Efficient Market Hypthesis)
	- Weak form: Past returns or volume on stocks are not helpful to predict future price (Technical Analysis is not useful)
	- Semi-Strong: Publically available information are already incorporated into current stock price
	- Strong: Both public & private information are incorporated into current stock price.

2. Markov Process follows 'Weak-form'
### Example: 
	- S0 = $40
	- S_1year ~ N(40,10) 10=std
	- delta S10 (0 to 1) = S1-S0 ~ N(0,10)
	- delta S20 = delta S10 + delta S21 ~ N(0, 10)
	- E(delta S20) = 0
	- Var(delta S20) = Var(delta S10 + delta S21) + 2 Cov(delta S10, delta S21)
	- As long as time is not overlapped stock prices between previous and later are independent.
	- Std(delta S20) = sqrt(2) * 10
	- delta S_T0 ~ N(0, sqrt(T)*10)

### Wiener Process
	- delta z = epsilon * sqrt(delta t)
	- independant condition
	- delta z ~ N(0, sqrt(delta t))

1. Properties of a Wiener Process
	- Mean of [z(T) - z(0)] is 0
	- Variance of [z(T) - z(0)] is T
	
2. dX = a * dt + b * dz
	- a*dt = drift term (deterministic term)
	- b*dz = volatility term (stochastic term)
3. dx ~ N(a * dt, b * sqrt(dt))
4. X_T ~ N(a * T, b * sqrt(T))

dr = a(r_bar - r) * dt + b * dz => mean-reverting process,
