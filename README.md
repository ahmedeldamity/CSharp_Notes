<h1 align="center">C# Notes</h1>

# Programming Paradigms

![image](https://github.com/user-attachments/assets/91721d3e-7426-41e1-b60d-ec77c5f8370c)

- Linear | Sequential Programming

في البداية كنا بنكتب كود بطريقة الـ (Linear Code) وكان عنده مشكلة فى الـ (Maintenance) يعنى العميل لو حب يغير او يعدل فى الكود (Change Request) ف لو عايز اعدل ف سطرين بس كان مكلف جدا والكود كان (Spaghetti Code) ف لو غيرت ف سطر هيروح مغير فى كله ووممكن الكود كله يضرب ومكنش عندى (Function, Class, Object) والكود كان عباره عن (Single Block Code)

- Structured | Functional Programming

وهنا بدأنا نقسم الكود عن طريق Funtion بحيث تقدر تعمل Calls لبعضها ودا كان عن طريق لغة الـ `c` في الوقت دا ولكن كان عندها عيوب وهما: 

الاول: `Global Variable` ودا ليه مشكله لان بيكون في اكتر من Function مستخدمينة ف ممكن Function معينة تغير في Variable دا وبالتالي باقي Function مش هتستخدم Data الاصلية اللي كانت موجودة في Variable دا  

التاني: `Stand Alone Function` ودي بتكون مش تابعة لـ حاجة معينة ومش موجودة فى Class 

ف كان حل المشكلة دي هي OOP

- OOP (Object-oriented programming)

`Not Pure OOP`

اما الـ OOP هو الوحدة االساسية بتاعته الـ class ومن خلالة قدرت اسيطر على العيوب السابقة واول لغة طلعت اقدر اكتب بيها OOP كانت لغة SmallTalk ووقتها كان صعب جدا انى اكون شغال بلغة ال c واغير للغة تانيه زي اللغة دي ف الحل وقتها كان ان هما عملو لغة تانيه وهي ال ++c 
وكانت عباره عن لغه الـ C ومذودين عليها ال OOP ولكن اللغه دي في الحقيقة هي Not pure OOP لان جواها تقدر تكتب بلغة ال C وتقدر تكتب OOP فبالتالى بالرغم من انها خلتني اقدر اكتب OOP ولكن مازلت اقدر اكتب جواها (Stand Alone Function, Global Variable)

`Pure OOP`

شركة Sun Microsystems عملت لغة ال Java ودول بقا خدو ال CPP وخلوها Pure OOP يعنى من خلالها معدتش اقدر اكتب (Stand Alone Function, Global Variable) واللي حصل بعد كدا ان شركة Oracle اشترت Sun فأصبحت هي المالك الفعلي للغة البرمجة Java

شركة Microsoft عملت لغة اسمها COOL وبعدين غيروا الاسم وبقا ++++C وبعدين غيروه تاني بقا #C وبرضه دي انت نسخة من CPP ولكن كانت Pure OOP

# Pre Dot Net

![image](https://github.com/user-attachments/assets/b1bfb05e-10c3-480b-8d42-2896175d7595)


شركة Microsoft كان عندها عده لغات زي Visual CPP, Visual Basic, Delphi 
ودي كانت Life Cycle قبل Dot Net :

اول حاجه بكتب الكود بتاعى وبعد كدا Compiler بياخد الكود بتاعى ويحوله الى (1|0) Native Code ف Project بيكون Platform Dependent يعنى بيعتمد على ال Platform اللى بيتعمل عليها البرنامج بتاعى بمعني اني لو عملت Compile للبرنامج بتاعى على Windows
هيطلعلي ال Native Code الخاص بـ Windows ولو عملت علي Linux هيطلعي Native Code الخاص بـ Linux ونفس الموضوع برضه في MAC ودا لان المعمارية بتاعة كل Platform فيهم مختلفة عن التانية

ف كانت اول مشكلة (Platform Dependent): انى مقدرش اعمل Project يشتغل على كل Platforms المختلفة
تاني مشكلة (Not Cross Language):  اني مقدرش اشتغل فى نفس البروجكت بـ أكتر من لغة

# With Dot Net 2002

![image](https://github.com/user-attachments/assets/17916f4c-f4cb-471f-a11a-ee197c853a6a)
_________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/9372b2dc-8547-4d7b-9339-2a7d11570b9f)
_________________________________________________________________________________________

المشكلة الاولي:-
هنا في Dot Net Framework مايكروسوفت اشتغلت بـ JIT عشان تحل المشكلة الاولي و Project يكون Cross Platform ولكن هيا محلتش المشكلة كلها لانها عملت JIT Compiler بس لـ Windows بس فبالتالي Linux and MAC معندهمش JIT يترجم dll لـ Native Code الخاص بكل OS منهم فبالتالي المشكلة الاولي فاضلها ان Microsoft تعمل JIT خاص بـ MAC وواحد تاني خاص بـ Linux بحيث لما اخد dll بتاعي من علي Windows واجي اشغل الـ Project علي Linux مثلا فـ يكون معايا JIT خاص ب Linux يكون قادر يحولي dll دا لـ Native Code بتاع Linux ونفس الكلام في MAC برضه

المشكلة التانية:-
ودي اتحلت خلاص لان مهما كانت اللغه اللي هنشتغل بيها ف كدا كدا هتتحول لـ نفس dll بمعني اننا لو اشتغلنا ب لغه #C ولغه VB في مشروع واحد ف هما الاتنين هيتحولوا لـ dll واحد


![image](https://github.com/user-attachments/assets/46b0753b-731d-45b1-adce-abf673859e0d)

في مجموعة من Developers عملوا Mono Framework ودا كان Parallel Implementation For Dot Net Framework بحيث انهم اعادوا كتابة Dot Net Framework بحيث يشتغل على Linux and MAC بجانب Windows طبعا ولكن كان عندهم مشاكل منهم:

المشكلة الاولي: Many enterprises and companies trusted Microsoft more for long-term support and stability

المشكلة التانية: Performed worse because Mono's (JIT) compilation and runtime weren't as optimized as Microsoft’s .NET runtime on Windows
_______________________________________________________________________________________

# Value Type & Refrence Type

![image](https://github.com/user-attachments/assets/734bee6e-ba99-487a-ae36-d80d6a9709cb)





















