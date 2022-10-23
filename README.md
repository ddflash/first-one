t=int(input())
p=[]
q=[]
def check(s):
    a=[]
    num=0
    dian=0
    for i in s:
        if i=='.':
            dian+=1
            a.append(num)
        elif i==':':
            if dian!=3:
                return False
            else:
                a.append(num)
        elif i>='0' and i<='9':
            num=num*10+int(i)
        else:
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
        else:
            print("OK")
            p.append(s)
            q.append(0)
    else:
        s=s[7:]
        f=check(s)
        if f==False:
            print("ERR")
        elif s in p:
            now=p.find(s)
            q[now]+=1
            print(q[now])
        else:
            print("FAIL")
