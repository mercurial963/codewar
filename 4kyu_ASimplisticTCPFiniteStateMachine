#https://www.codewars.com/kata/54acc128329e634e9a000362/train/python
state ={
    "CLOSED": ["APP_PASSIVE_OPEN","APP_ACTIVE_OPEN"],
    "LISTEN": ["RCV_SYN","APP_SEND","APP_CLOSE"],
    "SYN_RCVD": ["APP_CLOSE","RCV_ACK"],
    "SYN_SENT": ["RCV_SYN","RCV_SYN_ACK","APP_CLOSE"],
    "ESTABLISHED": ["APP_CLOSE","RCV_FIN"],
    "FIN_WAIT_1": ["RCV_FIN","RCV_FIN_ACK","RCV_ACK"],
    "CLOSING": ["RCV_ACK"]        ,
    "FIN_WAIT_2": ["RCV_FIN"]     ,
    "TIME_WAIT": ["APP_TIMEOUT"]  ,
    "CLOSE_WAIT": ["APP_CLOSE"]   ,
    "LAST_ACK": ["RCV_ACK"]       ,
}
next_state ={
     "CLOSED":      {"APP_PASSIVE_OPEN" : "LISTEN",
                     "APP_ACTIVE_OPEN"  : "SYN_SENT"},
     "LISTEN":      {"RCV_SYN"          : "SYN_RCVD",
                     "APP_SEND"         : "SYN_SENT",
                     "APP_CLOSE"        : "CLOSED"},
     "SYN_RCVD":    {"APP_CLOSE"     : "FIN_WAIT_1",
                     "RCV_ACK"        : "ESTABLISHED"},
     "SYN_SENT":    {"RCV_SYN"        : "SYN_RCVD",
                     "RCV_SYN_ACK"    : "ESTABLISHED",
                     "APP_CLOSE"      : "CLOSED"},
     "ESTABLISHED": {"APP_CLOSE"   : "FIN_WAIT_1",
                     "RCV_FIN"     : "CLOSE_WAIT"},
     "FIN_WAIT_1":  {"RCV_FIN"      : "CLOSING",
                     "RCV_FIN_ACK"  : "TIME_WAIT",
                     "RCV_ACK"      : "FIN_WAIT_2"},
     "CLOSING":     {"RCV_ACK"         : "TIME_WAIT"},
     "FIN_WAIT_2":   {"RCV_FIN"      : "TIME_WAIT"},
     "TIME_WAIT" :   {"APP_TIMEOUT"   : "CLOSED"},
     "CLOSE_WAIT":   {"APP_CLOSE"    : "LAST_ACK"},
     "LAST_ACK"  :   {"RCV_ACK"        : "CLOSED"}
}
def traverse_TCP_states(events):
    current_state = "CLOSED"  # initial state, always
    x = 0
    print(state["CLOSED"])
    while(x < len(events)):
        if events[x] in state[current_state] :
            current_state = next_state[current_state][events[x]]
            
            x = x+1
        else :
            return "ERROR"
            break
        print (current_state)
    # if current_state
    return current_state
    
# traverse_TCP_states(["APP_ACTIVE_OPEN","RCV_SYN_ACK","RCV_FIN"])
