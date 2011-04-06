Laser
=====

Beam information at the speed of light -- dirt-simple RPC for Node.js.

(This has been tested up to Node.js v0.4.5.)

Install
-------

Get [npm](http://github.com/isaacs/npm#readme) if you don't already have it,
and then just run `npm install choreographer`.

Usage
-----

As easy as

    //on the server
    var beam = require('laser').beam;
    beam.everyone('send', function(name, message) {
      beam.everyone.receive(name, message);
    });

and on the client

    <script type="text/javascript" src="/laser/beam.js"></script>
    <script type="text/javascript">
      beam('receive', function(name, message) {
        $('#messages').append('<p>' + name + ': ' + message);
      });
      $('#send-button').click(function() {
        beam.send($('#text-input').val());
        $('#text-input').val('');
      });
    </script>
