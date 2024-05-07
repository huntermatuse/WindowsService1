Based on a tutorial on youtube for internal projects. 

I have 'improved' the code to append to the log file instead of writing over it. 

```C#
private void WriteToFile(string Message)
{
    string path = AppDomain.CurrentDomain.BaseDirectory + "\\Logs";
    if (!Directory.Exists(path))
    {
        Directory.CreateDirectory(path);
    }

    string filepath = AppDomain.CurrentDomain.BaseDirectory + "\\Logs\\ServiceLog_" + DateTime.Now.ToShortDateString().Replace('/', '_') + ".txt";

    using (StreamWriter sw = new StreamWriter(filepath, true))
    {
        sw.WriteLine(Message);
    }
}
```



https://www.youtube.com/watch?v=67DtZbPYNKg