NAME
    isbn-match.pl

DESCRIPTION
    Compares two lists of ebooks and print books respectively, and produces
    a list of titles matched by ISBN.

    Each list needs to be a tab-delimited csv file, as output by Excel.

    We first produce the lists using Alma Analytics reports.

    The first column of each list must contain the ISBNs for each title.
    Multiple ISBNs are separated by "; ". The remaining columns can be as
    desired, but typically title, author, publisher, pub. date, plus call
    number or interface name for p- and e- respectively.

VERSION
    Version 2015.05.13

PROCESSING
    First we read in all the records from the ebooks list, and build a hash
    of records with each ISBN as key. (So a record with multiple ISBNs will
    be stored multiple times.)

    Then we read in the records from the print list. For each record, get
    each ISBN and check the hash to see if it exists. If it does, then we
    have matched with an ebooks, so print the print record and the ebook
    record from the hash, and continue with the next print record.

    At the end of processing, we have a list of matched p- and e- titles in
    csv format which you can import into Excel.

AUTHOR
    Steve Thomas <stephen.thomas@adelaide.edu.au>

LICENCE
    Copyright 2015 Steve Thomas

    Permission is hereby granted, free of charge, to any person obtaining a
    copy of this software and associated documentation files (the
    "Software"), to deal in the Software without restriction, including
    without limitation the rights to use, copy, modify, merge, publish,
    distribute, sublicense, and/or sell copies of the Software, and to
    permit persons to whom the Software is furnished to do so, subject to
    the following conditions:

    The above copyright notice and this permission notice shall be included
    in all copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
    OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
    MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
    IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
    CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
    TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
    SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
