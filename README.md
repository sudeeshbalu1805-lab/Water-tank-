% Closed Loop Water Tank Simulation
A = 1;      
Kp = 1.5;   
s = tf('s');
G = 1/(A*s); 
% Feedback system
H_desired = 2; 
sys_cl = feedback(Kp*G,1); 

% Step response
figure;
step(H_desired*sys_cl)
title('Closed Loop Water Tank Response')
ylabel('Tank Level (m)')
xlabel('Time (s)')
grid on
