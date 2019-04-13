# ruuvitag-upload

A tool for collecting a set of ruuvitag sensor measurements
and uploading them for further processing.

The measurements are formatted as JSON with the following
structure

    {
        \"<ALIAS>\": {
            \"address\": \"XX:XX:XX:XX:XX:XX\",
            \"timestamp\": <seconds since unix epoch>,
            \"humidity\": <0-100%>,
            \"pressure\": <kPa>,
            \"temperature\": <Celcius>,
            \"battery_potential\": <volts>
        },
        ...
    }

where ALIAS will either be the address of the sensor, or
an alias that you can define.

Parts of the program are inspired by and some parts are copied from [ruuvitag-listener](https://github.com/lautis/ruuvitag-listener).

## USAGE

    ruuvitag-upload [--url=URL] <sensor>...
    ruuvitag-upload -h | --help
    ruuvitag-upload --version

## ARGUMENTS

    <sensor>...

        A sensor address and optionally a human-readable
        alias. You can either specify the address as
        XX:XX:XX:XX:XX:XX or you can attach a human-
        readable alias to the address
        XX:XX:XX:XX:XX:XX=mysensor.

## OPTIONS

    -u URL, --url=URL

        Where the measurements are uploaded to. If you don't
        specify this, the measurements are written to stdout.

    -h, --help

        Show this message.

    --version

        Show the version number.
