# BSmodel
C++
BS model
reference: https://www.quantstart.com/articles/C-Explicit-Euler-Finite-Difference-Method-for-Black-Scholes/

## PayOff
This class represents the pay-off functionality of an option. It is also a functor. We have already made extensive use of it in our Monte Carlo options pricing articles. I have added the code listing below for completeness.

## VanillaOption
This is a simple class that encapsulates the option parameters. We are using it as well as PayOff as we will want to extend the FDM solver to allow more exotic options in the future.
ConvectionDiffusionPDE - This is an abstract base class designed to provide an interface to all subsequent derived classes. It consists of pure virtual functions representing the various coefficients of the PDE as well as boundary and initial conditions.

## BlackScholes PDE 
This inherits from ConvectionDiffusionPDE and provides concrete implementations of the coefficients and boundary/initial conditions specific to the Black-Scholes equation.

## FDMBase
This is another abstract base class that provides discretisation parameters and result storage for the Finite Difference scheme. It possesses a pointer to a ConvectionDiffusionPDE.
FDMEulerExplicit - This inherits from FDMBase and provides concrete methods for the Finite Difference scheme methods for the particular case of the Explicit Euler Method, which we described above.