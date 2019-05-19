# Anc Shell or AncShell
The special command interpreter. Can dynamic connect .DLL libraries

How to add DLL for load:



0. Run and Close AncShell (if file `adjuncts.txt` is not exsists),
1. Edit `adjuncts.txt` and add line `yourlib.dll` to end line file,
2. Save and close file `adjuncts.txt`,
3. Run AncShell.exe!

Your DLL library should have this  code for init by Anchsell:

`````csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Addons
{
    class __loadme
    {
        public bool Register( Type ShellType ) {
            
            //we return true if lib success loaded
            return true;
        }
        
        public bool RunCommand(string cmd, string[] args) {

            switch (cmd) {

                case "somecmd":

                      //place here your code
                      
                    return true;
                    break;

            }

            return false; //nothing to do

        }
    }
}
