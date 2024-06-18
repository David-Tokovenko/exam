using System;
public interface Lamp
{
    string Type { get; set; }
    string Vurobnuk { get; set; }
    int Potyzhnist { get; set; }
    string ElementType { get; set; }
    int ElementCount { get; set; }
    void PrintLampDetails(); void ChangePotyzhnist(int newPotyzhnist);
}
public interface Camera
{
    string Type { get; set; }
    string Vurobnuk { get; set; }
    int Sensitiv { get; set; }
    void PrintCameraDetails(); void ChangeSensitiv(int newSensitiv);
}
public class PhotoStudio : Lamp, Camera
{
    public string Type { get; set; }
    public string Vurobnuk { get; set; }
    public int Potyzhnist { get; set; }
    public string ElementType { get; set; }
    public int ElementCount { get; set; }
    public int Sensitiv { get; set; }
    public void PrintLampDetails()
    {
        Console.WriteLine($"Тип лампи: {Type}, виробник: {Vurobnuk}, потужнiсть у люменах: {Potyzhnist}, тип елементiв: {ElementType}, кiлькість елементiв: {ElementCount}");
    }
    public void ChangePotyzhnist(int newPotyzhnist)
    {
        Potyzhnist = newPotyzhnist;
    }
    public void PrintCameraDetails()
    {
        Console.WriteLine($"Тип камери {Type}, виробник: {Vurobnuk}, свiтлочутливiсть оптичного об'єктиву: {Sensitiv}");
    }
    public void ChangeSensitiv(int newSensitiv)
    {
        Sensitiv = newSensitiv;
    }
}
class Program
{
    static void Main()
    {
        PhotoStudio photostudio1 = new PhotoStudio
        {
            Type = "світлодіодна",
            Vurobnuk = "Orsam",
            Potyzhnist = 1000,
            ElementType = "LED",
            ElementCount = 10,
            Sensitiv = 300
        };
        PhotoStudio photostudio2 = new PhotoStudio
        {
            Type = "металогалогенна",
            Vurobnuk = "Philips",
            Potyzhnist = 1500,
            ElementType = "LED",
            ElementCount = 5,
            Sensitiv = 600
        };
        Console.WriteLine("Деталi першоi студii:"); photostudio1.PrintLampDetails();
        photostudio1.PrintCameraDetails();
        Console.WriteLine("\nДеталi другоi студii:"); photostudio2.PrintLampDetails();
        photostudio2.PrintCameraDetails();
        photostudio1.ChangeSensitiv(600);
        Console.WriteLine("\nЗмiненi деталi першоi студii:"); photostudio1.PrintCameraDetails();
    }
}
