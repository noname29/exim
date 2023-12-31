# Make file for building Exim's lookup modules.
# This is called from the main make file, after cd'ing
# to the lookups subdirectory.
#
# Copyright (c) The Exim Maintainers 2021

# nb: at build time, the version of this file used will have had some
#     extra variable definitions and prepended to it and module build rules
#     interpolated below.

# MAGIC-TAG-MODS-OBJ-RULES-GO-HERE


all:             lookups.a lf_quote.o lf_check_file.o lf_sqlperform.o $(MODS)

lookups.a:       $(OBJ)
		 @$(RM_COMMAND) -f lookups.a
		 @echo "$(AR) lookups.a"
		 @$(AR) lookups.a $(OBJ)
		 $(RANLIB) $@

.SUFFIXES:       .o .c .so
.c.o:;           @echo "$(CC) $*.c"
		 $(FE)$(CC) -c $(CFLAGS) $(INCLUDE) $*.c

.c.so:;          @echo "$(CC) -shared $*.c"
		 $(FE)$(CC) $(LOOKUP_$*_INCLUDE) $(LOOKUP_$*_LIBS) -DDYNLOOKUP $(CFLAGS_DYNAMIC) $(CFLAGS) $(INCLUDE) $(DLFLAGS) $*.c -o $@

lf_check_file.o: $(HDRS) lf_check_file.c  lf_functions.h
lf_quote.o:      $(HDRS) lf_quote.c       lf_functions.h
lf_sqlperform.o: $(HDRS) lf_sqlperform.c  lf_functions.h

cdb.o:           $(HDRS) cdb.c
dbmdb.o:         $(HDRS) dbmdb.c
dnsdb.o:         $(HDRS) dnsdb.c
dsearch.o:       $(HDRS) dsearch.c
ibase.o:         $(HDRS) ibase.c
ldap.o:          $(HDRS) ldap.c
lmdb.o:          $(HDRS) lmdb.c
json.o:          $(HDRS) json.c
lsearch.o:       $(HDRS) lsearch.c
mysql.o:         $(HDRS) mysql.c
nis.o:           $(HDRS) nis.c
nisplus.o:       $(HDRS) nisplus.c
oracle.o:        $(HDRS) oracle.c
passwd.o:        $(HDRS) passwd.c
pgsql.o:         $(HDRS) pgsql.c
readsock.o:      $(HDRS) readsock.c
redis.o:         $(HDRS) redis.c
spf.o:           $(HDRS) spf.c
sqlite.o:        $(HDRS) sqlite.c
testdb.o:        $(HDRS) testdb.c
whoson.o:        $(HDRS) whoson.c

cdb.so:           $(HDRS) cdb.c
dbmdb.so:         $(HDRS) dbmdb.c
dnsdb.so:         $(HDRS) dnsdb.c
dsearch.so:       $(HDRS) dsearch.c
ibase.so:         $(HDRS) ibase.c
json.so:          $(HDRS) json.c
ldap.so:          $(HDRS) ldap.c
lmdb.so:          $(HDRS) lmdb.c
lsearch.so:       $(HDRS) lsearch.c
mysql.so:         $(HDRS) mysql.c
nis.so:           $(HDRS) nis.c
nisplus.so:       $(HDRS) nisplus.c
oracle.so:        $(HDRS) oracle.c
passwd.so:        $(HDRS) passwd.c
pgsql.so:         $(HDRS) pgsql.c
redis.so:         $(HDRS) redis.c
spf.so:           $(HDRS) spf.c
sqlite.so:        $(HDRS) sqlite.c
testdb.so:        $(HDRS) testdb.c
whoson.so:        $(HDRS) whoson.c

# End
