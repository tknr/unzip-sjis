#!/usr/bin/perl
## http://linux.just4fun.biz/CentOS/CentOS%E3%81%A7Windows%E3%81%AE%E3%82%B7%E3%83%95%E3%83%88JIS%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E5%90%8D%E3%82%92%E5%90%AB%E3%82%80zip%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%82%92%E8%A7%A3%E5%87%8D%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95.html
use strict;
use warnings;
use Archive::Zip;
use Encode;

if (@ARGV != 1) {
  die "usage: $0 ZIPFILE\n";
}
my $zipfile = shift;
if (! -e $zipfile) {
  die "$zipfile don't exist\n";
} 
my $zip=Archive::Zip->new($zipfile);
my @items = $zip->memberNames();
my $utf8name;
foreach (@items) {
  my $utf8name = $_;
  Encode::from_to($utf8name, 'cp932', 'utf-8');
  print "extract : $utf8name\n";
  $zip->extractMember($_, $utf8name);
}

