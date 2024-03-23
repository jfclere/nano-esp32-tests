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
the sp_2048_norm_36() and co are in ./sp_c32.c (how to use them???)

#define FP_MAX_BITS 8192 in ${HOME}/Arduino/libraries/wolfssl/src/wolfssl/wolfcrypt/settings.h helps

#define DEBUG_WOLFSSL there too is nice to debug...
note:
WOLFSSL_MSG_EX("fp_exptmod_nct failed err = %d", FP_MAX_BITS);
helps to debug.
