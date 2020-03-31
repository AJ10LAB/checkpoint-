# checkpoint-
#checkpoint and restart mechanism


#include <stdlib.h>
#include <ckpt.h>
#include <sys/types.h>
#include <sys/mount.h>
#include <unistd.h>
#include <stdio.h>

do_remove(char *path_name)
{
    int cr = 0;
    if ((cr = ckpt_remove(path)) != 0) {
        printf("Remove checkpoint statefile %s failedn", path_name);
        return (cr);
    }
}

int ckpt_setup(struct ckpt_args *args[], size_t nargs)
{
    return(0);
}

main(int argc, char *argv[])
{
    int err = 0;
    if ((atcheckpoint(ckptSocket) == -1) ||
        (atcheckpoint(ckptXserver) == -1) ||
        (atrestart(restartSocket) == -1) ||
        (atrestart(restartXserver) == -1))
            perror("Cannot setup checkpoint and restart handling");
    exit(0);
}
