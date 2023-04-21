# WebApp1

Задача: Да се додаде Google sign in копче.

1 чекор: преку NuGet Packages го инсталираме пакетот microsoft.aspnetcore.authentication.google. Во зависност од која верзија на .Net core ја инсталираме соодветната верзија.


2 чекор: Во appsettings.Development.json го додаваме кодот:
"GoogleAuthSettings": {
    "ClientId": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    "ClientSecret": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
  }

-каде си ставаме наше Id и ClientSecret

3 чекор: Во Program.cs го додаваме кодот:
builder.Services.AddAuthentication().AddGoogle(googleOptions =>
{
    googleOptions.ClientId = builder.Configuration.GetSection("GoogleAuthSettings")
.GetValue<string>("ClientId");
    googleOptions.ClientSecret = builder.Configuration.GetSection("GoogleAuthSettings")
.GetValue<string>("ClientSecret");
});
  
  
