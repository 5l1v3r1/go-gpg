This library duplicates the basic behavior of the GPG library so you can use its functionality without deferring to an external executable or using a bridge to C.

# Encoding
Use a new `&gpg.Encoder{}` or just `gpg.Encode(key []byte, src io.Reader, dest io.Writer)`. The key is the public key including headers.

# Decoding
Use a new `&gpg.Decoder{}` or just `gog.Decode(key, passphrase []byte, src io.Reader, dest io.Writer)`. The key is the private key including headers. If the private key is encrypted with a passphrase you should provide it here, otherwise pass an empty byte slice (`[]byte{}`) as the second argument.