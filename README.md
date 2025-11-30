from nlp_log_analyzer import NLPLogAnalyzer
from behavior_agent import BehaviorAgent
from decision_agent import DecisionAgent
from automation_agent import AutomationAgent
from dashboard_agent import DashboardAgent

f = open("../data/sample_logs.txt").read().split("\n")

nlp = NLPLogAnalyzer()
behavior = BehaviorAgent()
decision_agent = DecisionAgent()
automation = AutomationAgent()
dashboard = DashboardAgent()

history = {"allowed_locations": ["Hyderabad", "Mumbai", "Delhi"]}

for log in f:
    parsed = nlp.parse(log)
    anomaly = behavior.detect_anomaly(history, parsed)
    decision = decision_agent.decide(anomaly)
    action_result = automation.execute(decision)
    print(dashboard.report(parsed, decision))# congenial-meme
This project implements a Netflix-style Multi-Agent AIOps framework to detect unauthorized multi-device logins, account sharing, bot traffic, and overload-induced service crashes on OTT platforms.  Using NLP-driven log intelligence, the system automatically:  Parses high-velocity streaming logs  Identifies 
