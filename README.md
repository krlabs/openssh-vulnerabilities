# Список вразливостей OpenSSH

Публікується з метою контролю безпеки сайтів на базі веб-серверів з OpenSSH. На замітку дослідникам та власникам електронних ресурсів. В рамках волонтерського проєкту "За вільний і безпечний UAnet!".

Дані вразливості були виявлені дослідниками KR. Laboratories в ході глобального аудиту ресурсів українського сегменту мережі Інтернет й можуть бути використані як легітимними пентестерами, так і зловмисниками для проведення різноманітних атак, зокрема: віддалене виконання коду (Remote Code Execution), несанкціонований доступ (Unauthorized Access), перехоплення даних "Людина посередині" (Man-in-the-Middle-Attack), Directory Traversal, Bruteforce Attack. Це може призвести до пошкодження або повної втрати даних на сервері, помилок конфігураці та багато іншого.  

Ми рекомендуємо українським веб-майстрам і системним адміністраторам регулярно оновлювати серверне програмне забезпечення та використовувати наші рекомендації щодо кібербезпеки, аби мінімізувати потенційні ризики.  

З приводу захисту веб-серверів пишіть нам на електронну скриньку: security[@]kr-labs.com.ua

| **CVE Ідентифікатор** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | **Опис** | **Exploit / PoC** |
|-----------------------------------------------------|----------|-------------|
| [**CVE-2007-2243**](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2007-2243)| Якщо ввімкнуто ChallengeResponseAuthentication, OpenSSH дозволяє віддаленим зловмисникам визначати існування облікових записів користувачів, намагаючись автентифікуватися через S/KEY, який відображає іншу відповідь, якщо обліковий запис користувача існує, подібна проблема до CVE-2001-1483. | [Експлойт](https://cxsecurity.com/issue/WLB-2007040138) |
| [**CVE-2016-6210**](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2016-6210)| Вразливість у OpenSSH, яка дозволяє зловмиснику дізнаватися про існування облікових записів на сервері за допомогою різниці у часу відповіді під час аутентифікації з недійсним ім’ям користувача. Це може бути використано для збору інформації про облікові записи перед подальшими атаками, такими як брутфорс. | [Експлойт1](https://www.exploit-db.com/exploits/40136) [Експлойт2](https://gitlab.com/kar0nt3/ssh-users-enumeration-by-cve-2016-6210/-/blob/master/ssh_user_times_tester.py) [Експлойт3](https://hackerone.com/reports/776461) |
| [**CVE-2016-20012**](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2016-20012)| Дозволяє атакуючим, які підозрюють, що певна комбінація імені користувача та відкритого ключа відома серверу SSH, перевірити, чи ця підозра правильна. Це відбувається тому, що виклик надсилається лише тоді, коли ця комбінація може бути дійсною для сеансу входу. ПРИМІТКА: Постачальник не визнає енумерацію користувачів як вразливість. | [Експлойт](https://github.com/aztec-eagle/cve-2016-20012) |
| [**CVE-2017-15906**](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-15906)| OpenSSH вразливий до відмови в обслуговуванні, викликаної помилкою у функції process_open() у режимі лише для читання. Віддалений автентифікований зловмисник може використати цю вразливість для створення файлів нульової довжини та спричинити відмову в обслуговуванні. | [PoC](https://github.com/vulhub/vulhub/blob/master/tikiwiki/CVE-2020-15906/poc.py) |
| [**CVE-2018-15473**](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2018-15473)| Вразливість в модулях SSH auth2-gss.c, auth2-hostbased.c та auth2-pubkey.c дозволяє проводити енумерацію імен користувачів. Знаючи логін, атакуючий може підібрати пароль до нього. | [Експлойт1](https://www.exploit-db.com/exploits/45210) [Експлойт2](https://www.exploit-db.com/exploits/45939) [Експлойт3](https://github.com/epi052/cve-2018-15473) [Експлойт4](https://github.com/Rhynorater/CVE-2018-15473-Exploit) [Експлойт5](https://packetstormsecurity.com/files/150621/OpenSSH-User-Enumeration.html) [PoC](https://github.com/trimstray/massh-enum) |
| [**CVE-2018-15919**](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2018-15919)| Вразливість в модулі auth2-gss.c може бути використана віддаленим зловмисником, щоб провести атаку енумерації і дізнатися імена усіх користувачів, зареєстрованих на SSH-сервері. | [Деталі](https://www.openwall.com/lists/oss-security/2018/08/24/1) |
| [**CVE-2018-20685**](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2018-20685)| Вразливість дозволяє віддаленим SSH-серверам обходити заплановані обмеження доступу за допомогою спеціально сформованих імен файлів, таких як "." або порожнє ім'я файлу. Це може призвести до несанкціонованої модифікації дозволів цільового каталогу на стороні клієнта. | [Деталі](https://my.f5.com/manage/s/article/K11315080) |
| [**CVE-2019-6109**](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-6109)| Вразливість полягає у тому, що віддалений сервер може підробити стандартний вивід інформації в консолі під час виконання scp-команди. Віддалений сервер може надіслати клієнту підроблені текстові повідомлення, вводячи користувача в оману щодо переданих файлів. | [Деталі](https://docs.ssh-mitm.at/_sources/vulnerabilities/CVE-2019-6109.rst.txt) |
| [**CVE-2019-6110**](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-6110)| Коли клієнт використовує команду scp для копіювання файлів із сервера, віддалений сервер (або зловмисник типу Man-in-The-Middle) може надсилати зловмисно сформовані повідомлення про прогрес передачі файлів. Ці повідомлення можуть бути використані для введення користувача в оману або відображення хибної інформації. | [Експлойт1](https://www.exploit-db.com/exploits/46193) [Експлойт2](https://0day.today/exploit/32009) [PoC](https://www.youtube.com/watch?v=1iVGlDfKx9A)|
| [**CVE-2019-6111**](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-6111)| Вразливість є логічним продовженням двох попередніх. Зловмисний сервер (або зловмисник типу Man-in-The-Middle) може маніпулювати виводом клієнта. | [Експлойт1](https://www.exploit-db.com/exploits/46193) [Експлойт2](https://gist.github.com/mehaase/63e45c17bdbbd59e8e68d02ec58f4ca2) |
| [**CVE-2020-14145**](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-14145)| Вразливість приводить до витоку інформації при підключенні до SSH під час узгодження алгоритмів. Це дозволяє зловмисникам типу "Man-in-the-Middle" націлюватися на початкові спроби підключення. | [PoC](https://github.com/ssh-mitm/ssh-mitm/blob/master/sshmitm/plugins/session/cve202014145.py) |
| [**CVE-2020-15778**](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-15778)| Дозволяє виконувати довільні команди на стороні клієнта через неналежну обробку команд у SSH-конфігурації, коли використовується функція scp або sftp. Функція toremote в scp.c вразлива до атаки Eval / Command Injection. Вразливість була повідомлена як спірна , оскільки постачальник (OpenSSH) заявив, що вони навмисно не перевіряють певні «аномальні передачі аргументів», оскільки це може порушити існуючі робочі процеси. | [PoC](https://www.facebook.com/watch/?v=350435662788591&locale=sw_KE) [Експлойт](https://github.com/Neko-chanQwQ/CVE-2020-15778-Exploit) |
| [**CVE-2021-41617**](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-41617)| Вразливість виникає через помилку в механізмі обробки конфігурацій, які передаються у файлі authorized_keys. Функція AuthorizedKeysCommand може використовувати дані із підробленого файла ключів для запису у непередбачувані місця в системі. | N/A | 
| [**CVE-2021-36368**](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-36368)| Якщо клієнт використовує аутентифікацію за допомогою публічного ключа з пересиланням агента (agent forwarding) без встановлення параметра -oLogLevel=verbose, зловмисник може непомітно модифікувати сервер, додавши підтримку опції аутентифікації "None". У такому випадку користувач не зможе визначити, чи підтверджує FIDO-аутентифікація намір підключитися до цього сервера, чи дозволяє цьому серверу підключитися до іншого сервера від імені користувача. Проте розробники OpenSSH стверджують, що це не є обходом аутентифікації, оскільки жодні механізми не обходяться. | N/A | 
[**CVE-2023-38408**](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2023-38408)| Функція PKCS#11 в ssh-agent у OpenSSH до 9.3p2 має недостатньо надійний шлях пошуку, що призводить до віддаленого виконання коду (RCE), якщо ssh-агент пересилається до системи, контрольованої зловмисником. (Код у /usr/lib, який завантажується в ssh-agent є вразливим.) ПРИМІТКА: ця проблема існує через неповне виправлення для CVE-2016-10009. | [PoC1](https://www.qualys.com/2023/07/19/cve-2023-38408/rce-openssh-forwarded-ssh-agent.txt) [PoC2](https://github.com/kali-mx/CVE-2023-38408) [PoC3](https://github.com/LucasPDiniz/CVE-2023-38408) [Деталі](https://www.vicarius.io/vsociety/posts/exploring-opensshs-agent-forwarding-rce-cve-2023-38408)|
[**CVE-2023-48795**](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2023-48795)| Вразливість у протоколі SSH, яка дозволяє зловмисникам знижувати рівень безпеки з'єднання шляхом маніпуляції повідомленнями під час встановлення з'єднання, т.зв Terrapin Attack. У реальному сценарії зловмисник може використати цю вразливість, щоб перехопити конфіденційні дані або отримати контроль над критично важливими системами за допомогою доступу з правами адміністратора.| [PoC](https://hackerone.com/reports/2446531) |
[**CVE-2023-51385**](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2023-51385)| Якщо ім'я користувача або хоста містить спеціальні символи оболонки (shell metacharacters) і це ім'я використовується в токенах розширення в певних ситуаціях, може бути проведена атака Command OS Injection. Наприклад, ненадійний Git-репозиторій може містити підмодуль з такими символами в імені користувача або хоста. Це може призвести до виконання небажаних команд на локальній машині. | [PoC1](https://vin01.github.io/piptagole/ssh/security/openssh/libssh/remote-code-execution/2023/12/20/openssh-proxycommand-libssh-rce.html) [PoC2](https://github.com/vin01/poc-proxycommand-vulnerable) |
[**CVE-2024-6387**](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2024-6387)| Критична вразливість OpenSSH, відома як RegreSSHion. Дозволяє віддаленим неавтентифікованим зловмисникам виконувати довільний код з привілеями root. Ця вразливість виникає через умови гонки в обробнику сигналів, що можуть бути викликані, якщо клієнт не проходить автентифікацію протягом заданого часу LoginGraceTime (за замовчуванням 120 секунд). У таких випадках обробник сигналу SIGALRM викликає функції, які не є безпечними для асинхронного виклику, такі як syslog(), що може призвести до виконання довільного коду. Ця помилка вже була виправлена у 2006 році, коли їй було присвоєно CVE-2006-5051. Отже, нова помилка є регресією — повторною появою вже відомого дефекту через деякі зміни, внесені в код. | [Деталі](https://github.com/zgzhang/cve-2024-6387-poc/blob/main/regresshion.txt) [PoC1](https://github.com/lflare/cve-2024-6387-poc) [PoC2](https://www.youtube.com/watch?v=mk62SiX6CMU) |

## Джерела
- [OpenSSH Security log](https://www.openssh.com/security.html)
- [Medium. CVE-2023–38408 (OpenSSH Vulnerability to RCE](https://medium.com/@mane_csit2075/cve-2023-38408-openssh-vulnerability-to-rce-9e756a0369fd)
- [Medium. OpenSSH CVE-2018–15473 User Enumeration Vulnerability](https://medium.com/@Dhamuharker/openssh-cve-2018-15473-user-enumeration-vulnerability-1ad8c7b6c66f)
- [CyRisk. Mitigation Instructions for CVE-2020-15778](https://cyrisk.com/security/mitigation-instructions-for-cve-2020-15778)
- [SCP client multiply vulnerabilities](https://sintonen.fi/advisories/scp-client-multiple-vulnerabilities.txt)
- [SSH-MITM - ssh audits made simple](https://docs.ssh-mitm.at/index.html)
- [SSH-MITM on GitHub](https://github.com/ssh-mitm/ssh-mitm/)
- [F5. How do I verify the remote device key fingerprint before connecting to remote device from my BIG-IP system?](https://my.f5.com/manage/s/article/K000133503)
- [PICUS. OpenSSH regreSSHion CVE-2024-6387 Vulnerability: Exploitation & Mitigation](https://www.picussecurity.com/resource/blog/openssh-regresshion-cve-2024-6387-vulnerability-exploitation-mitigation)
- [Module Metasploit. SSH Enumeration](https://www.rapid7.com/db/modules/auxiliary/scanner/ssh/ssh_enumusers/)
- [Qualys. OpenSSH User name Enumeration Vulnerability : CVE-2018-15473](https://threatprotect.qualys.com/2018/08/30/openssh-user-name-enumeration-vulnerability-cve-2018-15473/)
- [Youtube. Using CVE-2018-15473 to enumerate valid users over SSH](https://www.youtube.com/watch?v=7ifJOon5-G8&t=1670s)
- [Youtube. Enumerating valid usernames via SSH (CVE-2018-15473)](https://www.youtube.com/watch?v=JvqBaZ0WnV4&t=1430s)
- [OpenSSH User Enumeration Vulnerability: a Close Look](https://blog.nviso.eu/2018/08/21/openssh-user-enumeration-vulnerability-a-close-look/)
- [Sekurak. OpenSSH – users enumeration – CVE-2018-15473](https://sekurak.pl/openssh-users-enumeration-cve-2018-15473/)
- [NMAP. Script ssh2-enum-algos](https://nmap.org/nsedoc/scripts/ssh2-enum-algos.html)
- [NMAP. SSH Brute script](https://nmap.org/nsedoc/scripts/ssh-brute.html)
- [PacketStorm. SSH Username Enumeration - Module exploit for Metasploit](https://packetstormsecurity.com/files/181223/SSH-Username-Enumeration.html)
- [SSH Pentesting -> Enumeration](https://cyberkhalid.github.io/posts/ssh-enum/)
- [INE Training Notes - by syselement. SSH enum](https://blog.syselement.com/ine/courses/ejpt/assessment-methodologies/3-enumeration/ssh-enum)
- [HackTricks. Pentesting SSH/SFTP](https://book.hacktricks.xyz/network-services-pentesting/pentesting-ssh)
- [SSH (Secure Shell) Pentesting](https://exploit-notes.hdks.org/exploit/network/protocol/ssh-pentesting/)
- [VeryLaxyTech. Pentest SSH Port 22](https://www.verylazytech.com/network-pentesting/ssh-port-22)
- [Less Secure SSH](https://www.less-secure.com/p/ssh.html)
- [Youtube. Red Teaming | SSH User Enumeration](https://www.youtube.com/watch?v=NX8njFqywAg)
- [Seclists.org. About OpenSSH "user enumeration" / CVE-2018-15473](https://seclists.org/oss-sec/2018/q3/170)
- [OffSec. Scanner SSH Auxiliary Modules](https://www.offsec.com/metasploit-unleashed/scanner-ssh-auxiliary-modules/)
- [Detection of Username EnumerationAttack on SSH Protocol: MachineLearning Approach](https://dspace.nm-aist.ac.tz/bitstream/handle/20.500.12479/1399/JA_CoCSE_2021.pdf;jsessionid=21356BDA53DD0CFD819966944550E867?sequence=1)
- [Youtube. SSH Enumeration.Assestment Methodologies](https://www.youtube.com/watch?v=W4EuJoi_Jsk)
- [Youtube. Enumerate ATT- SSH](https://www.youtube.com/watch?v=lkCAMj6RvQc)
- [Youtube. Brute Forcing SSH Using Wordlist](https://www.youtube.com/watch?v=ZUtyaR1-MOA)
- [Virtue. SSH Weak MAC Algorithms Enabled](https://www.virtuesecurity.com/kb/ssh-weak-mac-algorithms-enabled/)
- [INE Labs. SSH Recon Basic](https://www.coursesidekick.com/computer-science/3072971)
- [StackExchange. Infosecurity. Why OpenSSH deprecated DSA keys](https://security.stackexchange.com/questions/112802/why-openssh-deprecated-dsa-keys)
- [StackExchange. Infosecurity. Should DSA keys be considered deprecated?](https://security.stackexchange.com/questions/98441/should-dsa-keys-be-considered-deprecated)
- [Weak Diffie-Hellman and the Logjam Attack](https://weakdh.org)
- [SSH Hacking: How to Exploit Port 22 Vulnerabilities for Penetration Testing](https://medium.verylazytech.com/ssh-hacking-how-to-exploit-port-22-vulnerabilities-for-penetration-testing-601d257ee491)
- [STEFLAN. Linux Privilege Escalation – Exploiting Misconfigured SSH Keys](https://steflan-security.com/linux-privilege-escalation-exploiting-misconfigured-ssh-keys/)
- [Python tool SSH-audit](https://pypi.org/project/ssh-audit/)
- [PenTestPartners. How to abuse SSH keys](https://www.pentestpartners.com/security-blog/how-to-abuse-ssh-keys/)
- [SecurityAffairs. Compromised SSH keys used to access popular GitHub repositories](https://securityaffairs.com/37459/cyber-crime/compromised-ssh-keys.html)
- [Terrapin Attack](https://terrapin-attack.com)
- [Mitigating the SSH Terrapin Attack](https://www.nsoftware.com/kb/articles/terrapin)
- [Terrapin Vulnerability SCanner](https://github.com/RUB-NDS/Terrapin-Scanner)
- [OpenSSH Security Advisory: gcmrekey.adv](https://www.openssh.com/txt/gcmrekey.adv)
