# Hopefully

"Hopefully it works this time"

## What is this?

This is a very simple C# framework for dealing with unreliable services.
Sometimes the best way is to just retry it until it works.

We don't really know where to take this, but it was useful for our needs so we
figured we'd put it out there and maybe it'll be useful for you. If you can
think of a good way to extend it, pull requests are welcome.

## Usage

Install hopefully from NuGet, and then you can use it like so:

    var client = new HttpClient();
    var result = Procedure.Retry<string>(() =>
    {
        return client.DownloadString("http://unreliable.service/example.json");
    }, attempts = 10);

That's it, have fun.
