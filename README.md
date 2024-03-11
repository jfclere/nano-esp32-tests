# nano-esp32-tests
tests for arduino nano esp32

# routine for the random genration (copied from wolfSSL):
````
        int wc_GenerateSeed(OS_Seed* os, byte* output, word32 sz)
        {
            word32 rand;
            while (sz > 0) {
                word32 len = sizeof(rand);
                if (sz < len)
                    len = sz;
                /* Get one random 32-bit word from hw RNG */
                rand = esp_random( );
                XMEMCPY(output, &rand, len);
                output += len;
                sz -= len;
            }

            return 0;
        }
```
