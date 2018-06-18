---
layout: default
title: Contributing to Rust &mdash; language, compiler, and the standard library &middot; The Rust Programming Language
---

# Rust'a Katkı Sağlamak &mdash; Çeviri, Derleyici ve Standart Kütüphane

Derleyici ve standart kütüphane kaynak kodları ana depoda bulunur ve 
kaynak kodlarının bakımı deponun birincil konusu olduğundan dolayı konu
izleyicisindeki bir çok etiket kaynak kod bakımı ile ilgilidir. Rust
LLVM altyapı çevirisi için kullanılan [A-codegen]; hata ayıklayıcıları
tarafından kullanılan metanın oluşturulması kullanılan [A-debuginfo];
derleyicinin hata durumlarında oluşturduğu geribildirimler için kullanılan
[A-diagnostics]; standart kütüphane ile alakalı konular için kullanılan
[A-libs]; söz dizimi uzantıları ile ilgili konular için kullanılan [A-macros]
ve [A-syntaxext] ve veri tipleri için kullanılan [A-typesystem] etiketleri
diğer etiketlere göre daha fazla kullanılan etiketlerdir.

Derleyici mimarisi için detaylı yazılmış bir doküman bulunmamaktadır,
ancak [küçük bir doküman][rustc-guide] vardır. [Derleyiciyi oluşturan
kutular (crates) için yazılmış API dokümantasyonu][internal-docs],
kaynak kod tarayıcısına [Rust DXR] yardım edebildiği gibi sizin kaynak
kodunuzu da yönlendirme konusu yardımcı olabilir. Komut satırından
[`make tips`][tips] komutunu çalıştırarak açacağınız [Rust test ortamı
klavuzu][testsuite] size, Rust build sistemini etkili şekilde nasıl
kullanacağınızı öğretecektir.

For the foreseable future, one of the major thrusts of Rust compiler
development is converting its internals from operating directly off
the AST to working with an [intermediate representation called
MIR][mir]. This work is expected to open up many new possibilities by
simplifying the compiler and help is needed to e.g. create a MIR-based
translation pass, add MIR-based optimizations, and implement
incremental compilation. There is yet no single source for information
on work needed here, but ask on [internals.rust-lang.org] or
[#rust-internals] for guidance.

[It's embarrasing when our compiler crashes][ice] &mdash; the
dreaded 'internal compiler error' (ICE). The [I-ICE] label
tracks these, and they are often plentiful. These are usually
good bugs to start with because it's easy to know when you've fixed
them, and they're often relatively self-contained.

The performance of Rust code is one of its great advantages; and the
performance of the Rust compiler one of its great weaknesses. Any
improvements to either runtime or &mdash; especially &mdash; compiletime performance
are widely celebrated. The [I-slow] and [A-optimization] labels deal
with runtime performance, and [I-compiletime] with compiletime. We have
a [site that tracks compiletime performance][rustc-perf] on a number
of workloads. The `-Z time-passes` compiler flag can help debug
compiler performance, and Rust code can be profiled with standard
profilers like `perf` on Linux.

Major new features go through a [Request for Comments (RFC)][rfc]
process, by which the design is agreed upon. Though it is open to all,
it is a social process between developers who already have various
amounts of experience working together, and it is recommended to get
involved slowly &mdash; submitting a hasty RFC without understanding
the historical, technical, or social context is an easy way
to make a poor impression and come away disappointed. Read the
aforelinked readme file to understand best how it all works. Many
ideas have been debated in Rust's history, some rejected, some
postponed until the future, and the RFC [issue tracker][rfc-issues]
catalogs some wishlist ideas that have yet to make headway into the
language. Shortly before an RFC is accepted for implementation it
enters 'final comment period', indicated by the [final-comment-period
label on the rust-lang/rfcs repository][rfc-fcp]. Likewise, before a
feature is enabled in the stable compiler (called 'ungating') it
enters [final-comment-period in the rust-lang/rust
repository][issue-fcp]. Both FCPs are critical moments to get involved
and express opinions on the direction of the language, and are
advertised in the weekly subteam reports on [internals.rust-lang.org].

Meet other Rust compiler engineers in [#rustc], language
designers in [#rust-lang], and library designers in [#rust-libs].

<!--
TODO: guide to compile-time benchmarking
TODO: using the triage bot?
TODO: some of this RFC description could probably go in the RFC readme
-->


[#rust-internals]: https://client00.chat.mibbit.com/?server=irc.mozilla.org&channel=%23rust-internals
[#rust-lang]: https://client00.chat.mibbit.com/?server=irc.mozilla.org&channel=%23rust-lang
[#rust-libs]: https://client00.chat.mibbit.com/?server=irc.mozilla.org&channel=%23rust-libs
[#rustc]: https://client00.chat.mibbit.com/?server=irc.mozilla.org&channel=%23rustc
[A-codegen]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-codegen
[A-debuginfo]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-debuginfo
[A-diagnostics]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-diagnostics
[A-libs]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-libs
[A-macros]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-macros
[A-optimization]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-optimization
[A-syntaxext]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-syntaxext
[A-typesystem]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-typesystem
[I-ICE]: https://github.com/rust-lang/rust/labels/I-ICE
[I-compiletime]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AI-compiletime
[I-slow]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AI-slow
[Rust DXR]: https://dxr.mozilla.org/rust/source/src
[ice]: https://users.rust-lang.org/t/glacier-a-big-ol-pile-of-ice/3380
[internals-docs]: https://manishearth.github.io/rust-internals-docs
[internals.rust-lang.org]: https://internals.rust-lang.org/
[issue-fcp]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AB-unstable+label%3Afinal-comment-period
[mir]: https://github.com/rust-lang/rust/issues/27840
[rfc-fcp]: https://github.com/rust-lang/rfcs/pulls?q=is%3Aopen+is%3Apr+label%3Afinal-comment-period
[rfc-issues]: https://github.com/rust-lang/rfcs/issues
[rfc]: https://github.com/rust-lang/rfcs#table-of-contents
[rustc-guide]: https://github.com/rust-lang/rust/blob/master/src/librustc/README.md
[rustc-perf]: http://perf.rust-lang.org
[testsuite]: https://github.com/rust-lang/rust-wiki-backup/blob/master/Note-testsuite.md
[tips]: https://github.com/rust-lang/rust/blob/3d1f3c9d389d46607ae28c51cc94c1f43d65f3f9/Makefile.in#L48
