# Troubleshooting Report
## Incident 
What failed?
-The nginx server was inactive; the HTTP is not accessible.
-The command curl localhost was used to check if the server is accessible, the server was inaccessible.
## Expected State 
What should have been happening?
-The state of the nginx service should indicate active(running) so that the web server is accessible. The status was checked using command sudo systemctl status nginx.
## Observed State 
What actually happened?
-The state is inactive(dead), the nginx service was successfully deactivated. After the command sudo systemctl status nginx was used the status of the nginx was inactive(dead).
## Investigation 
What did you inspect?
-The status of the firewall rules were checked using the following command: sudo ufw status.
-The logs were inspected using command sudo journalctl -u nginx.
-Inspect the network using command: sudo ss -tulpn
## Evidence 
What evidence confirmed the problem?
-After the command sudo systemctl status nginx was used the status of the nginx was inactive. The network was inspected using command sudo ss -tulpn, the ports were not listening on ports 80 and 22, this confirmed that the data packets were not reaching the ports. 
## Root Cause 
What caused the failure?
-The nginx was deliberately stopped using the command sudo systemctl stop nginx. 
## Corrective Action 
What did you change?
-The nginx service was restarted using command sudo systemctl start nginx to start the nginx. 
-The nginx service was restarted. 
## Verification 
How did you prove the service was restored?
-The status of nginx service was checked using the command sudo systemctl status nginx to determine the status of the nginx service.
## Lessons Learned 
What did this incident teach you?
1. It is not appropriate to assume, always verify.
2. It is appropriate to use troubleshooting methods that uses correct engineering processes to troubleshoot web application that is inaccessible.
3. Troubleshooting methods involves 01-observe, 02-check, 03-investigate, 04-inspect logs, 05-form a hypothesis, 06-test, 07-correct, 08-verify and 09-document.
4. Verify before applying the corrective action because you may fix what is not broken which could disrupt or affect the entire production system.
5. Always verify the directory you are on using pwd command to check if you are applying the appropriate changes to the correct directory.
