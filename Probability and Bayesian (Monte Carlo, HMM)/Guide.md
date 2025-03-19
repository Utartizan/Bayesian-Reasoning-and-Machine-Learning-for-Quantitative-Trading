
## Part 1: Bayesian Updating

```

% Prior probability of stock price going up
prior_up = 0.5;
prior_down = 1 - prior_up;

% Likelihood of observing data given the stock goes up or down
% Let's say we observe a "signal" (e.g., positive news or price increase)
% P(signal | up) and P(signal | down)

likelihood_signal_given_up = 0.7;    % 70% chance of seeing this signal if stock goes up
likelihood_signal_given_down = 0.3;  % 30% chance of seeing this signal if stock goes down


% Observe a signal (e.g., a positive news event)
% Use Bayes' theorem to update our belief
% P(up | signal) = P(signal | up) * P(up) / P(signal)
% P(signal) = P(signal | up) * P(up) + P(signal | down) * P(down)

evidence = likelihood_signal_given_up * prior_up + likelihood_signal_given_down * prior_down;
posterior_up = (likelihood_signal_given_up * prior_up) / evidence;
posterior_down = (likelihood_signal_given_down * prior_down) / evidence;

% Display results

printf('Prior probability of stock going up: %.2f\n', prior_up);
printf('Posterior probability of stock going up after signal: %.2f\n', posterior_up);
```
### Results:

Prior Probability of Stock Going Up: 0.50

Posterior Probability of Stock Going up After Signal: 0.70



## Part 2: Stochastic Price Simulation (Geometric Brownian Motion)

```

% Simulate future stock price paths using GBM

S0 = 100;        % Defines the initial stock price
mu = 0.1;        % Defines the expected annual return (drift)
sigma = 0.2;     % Sets the annual volatility
T = 1;           % The time horizon (1 year)
dt = 1/252;      % Time step (1 trading day, assuming 252 trading days in a year)
n_steps = round(T/dt);  % Number of time steps
n_simulations = 1000;   % Number of simulated paths set to 1000.


% Brownian motion
rand_nums = randn(n_steps, n_simulations);
dW = sqrt(dt) * rand_nums;

% Simulate stock price paths using GBM: S(t+dt) = S(t) * exp((mu - 0.5*sigma^2)*dt + sigma*dW)
S = zeros(n_steps + 1, n_simulations);
S(1, :) = S0;  % Set initial price for all paths
for t = 1:n_steps
    S(t+1, :) = S(t, :) .* exp((mu - 0.5*sigma^2)*dt + sigma*dW(t, :));
end
```

### Result:
![image](https://github.com/user-attachments/assets/4afa8cd2-b62f-406b-b0ec-7f5dbc8deaba)






## Part 3: Plotting and Analysis

```
% Plotting a few simulated price paths
figure;
plot(0:dt:T, S(:, 1:5), 'LineWidth', 1.5);  % Plot first 5 paths
title('Simulated Stock Price Paths (Geometric Brownian Motion)');
xlabel('Time (Years)');
ylabel('Stock Price');
grid on;

% Calculate some basic statistics
final_prices = S(end, :);  % Prices at the end of the simulation
mean_final_price = mean(final_prices);
std_final_price = std(final_prices);
prob_up = mean(final_prices > S0);  % Probability price is higher than initial price

% Display statistics
printf('\nStochastic Simulation Results:\n');
printf('Mean final price: %.2f\n', mean_final_price);
printf('Standard deviation of final price: %.2f\n', std_final_price);
printf('Probability of price increase: %.2f\n', prob_up);
```

### Result:

Stochastic Simulation Results:

- Mean Final Price: 108.68

- Standard Deviation of Final Price: 21.94

- Probability of Price Increase: 0.63
