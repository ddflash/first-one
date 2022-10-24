t=int(input())
p=[]
q=[]
def check(s):
    a=[]
    num=0
    dian=0
    nn=0
    pi=1
    for i in s:
        if i=='.':
            dian+=1
            a.append(num)
            num=0
            pi=1
        elif i==':':
            if dian!=3 or nn:
                return False
            else:
                a.append(num)
                num=0
                nn+=1
                pi=1
        elif i>='0' and i<='9':
            if pi==0:
                return False
            if i=='0'and num==0:
                pi=0
            num=num*10+int(i)
        else:
            return False
    if dian!=3:
        return False
    for i in a:
        if i>=256:
            return False
    if num>=65536:
        return False
    return True


for tt in range(t):
    s=input()
    if s[0]=='S':
        s=s[7:] 
        f=check(s)
        if f==False:
            print("ERR")
        elif s in p:
            print("FAIL")
        else:
            print("OK")
            p.append(s)
            q.append(tt+1)
    else:
        s=s[7:]
        f=check(s)
        if f==False:
            print("ERR")
        elif s in p:
            for i in range(len(p)):
                if p[i]==s:
                    now=i
                    break
            print(q[now])
        else:
            print("FAIL")
