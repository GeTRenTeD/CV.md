# Summary 

## 1. Name and Surmame
Aleksey Savelev
## 2. Contacts
- Phone: +375 44 576 83 97 
- Email: alexeysavelev01@gmail.com
- GitHub: https://github.com/GeTRenTeD
- VK: https://vk.com/getrented
## 3. Brief information about yourself
I am a student in Belarusian-Russian university. I don`t have any expierience in work with production code, but i have worked with some interesting small projects. Now i am working on such a big project in team of 4 mates. I have a lot of hours of working on projects in Adobe programs like Photoshop, Ilustrator and Premiere. I like to create something new and inimitable.
## 4. Skills
Hard skills:
  - Programming languages: C#
  -  Version control systems: Git
  -  Development tools: Visual Studio, Visual Studio Code, Open Server, Brackets, Adobe Illustrator, Adobe Photoshop, Figma, Adobe Premiere.

Soft skills:

   - Adaptability: Being flexible and open to learning new programming languages, frameworks, and tools as technology evolves.
   - Teamwork: Collaborating with others, participating in group projects, and contributing positively to team dynamics.
   - Creativity: Thinking creatively to develop innovative solutions and user-friendly interfaces.
   - Analytical thinking: Applying logical reasoning and critical thinking skills to analyze problems and make informed decisions in software development.
   - Continuous learning: A willingness to stay updated with the latest trends, tools, and techniques in the field of software development.

## 5. Code examples
```C#
using System.Runtime.InteropServices;
using WIA;

namespace DetectionAndConversion
{
    public class Scan
    {
        public ImageFile WorkWithScan()
        {
            try
            {
                DeviceInfo? scanner = null;

                var deviceManager = new DeviceManager();

                for (int i = 1; i <= deviceManager.DeviceInfos.Count; i++)
                {
                    if (deviceManager.DeviceInfos[i].Type != WiaDeviceType.ScannerDeviceType)
                    {
                        continue;
                    }

                    scanner = deviceManager.DeviceInfos[i];

                    break;
                }

                if (scanner == null)
                {
                    throw new COMException("No scanner found");
                }

                var device = scanner.Connect();

                var ScanerItem = device.Items[1];

                var s = ScanerItem.Properties;



                Property prop = s.get_Item("6146");
                prop.set_Value(4);

                for (int f = 1; f < s.Count; f++)
                {

                    if (s[f].Name == "Vertical Resolution")
                    {
                        s[f].set_Value(300);
                    }
                    if (s[f].Name == "Horizontal Resolution")
                    {
                        s[f].set_Value(300);
                    }

                    //Console.WriteLine(s[f].Name + " " + s[f].get_Value());

                }

                return (ImageFile)ScanerItem.Transfer("{B96B3CAF-0728-11D3-9D7B-0000F81EF32E}");


            }
            catch (COMException ex)
            {

                Console.WriteLine(ex.Message);
                return null;
            }

        }
    }
}
```
## 6. Work experience and training projects
### Project 1: Passport scaner
- Skills used: C# programming, EPSON API
### Project 2: PC configurator
- Skills used: Figma, Adobe Photoshop, Adobe Ilustrator, NodeJS

## 7. Courses and trainings
- Completion of Stepik cousrses "Fundamental JavaScript"
## 8. Language
- Russian(native)
- English(B1)
## 9. Photo
![](/Img/CVphoto.jpg)