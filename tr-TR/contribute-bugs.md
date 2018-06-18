---
layout: default
title: Contributing to Rust &mdash; finding, triaging and fixing issues &middot; The Rust Programming Language
---

# Rust'a Katkı Sağlamak &mdash; Sorun Tespit Etmek, Önceliğini Belirmek ve Sorunu Çözmek

Rust projesinin günlük işleri [issue tracker] ve [pull request][PR]
adreslerinde yapılır, ve her zaman yardıma ihtiyaç duyulur. Rust'a
katkı sağlamanın en kolay yolu [E-easy] ve [E-mentor] etiketlerini
takip etmektir. Bu etiketler, yeni Rust programcıları için erişilebilir
anlamına gelir.

Tecrübeli bir Rust geliştiricisi, E-mentor konularında, problem çözmek
ve çözümü Github pull request ile göndermek için size tavsiyede bulunma
konusunda isteklidir. Geliştiriciler ile problem takibi sayfasının yorum
alanında veya IRC üzerinde isimlerini [@mentioning] yaparak veya onlara
elektronik posta göndererek problem hakkında iletişim kurabilirsiniz.
Rust geliştiricilerinin çok fazla elektronik posta aldığını ve bazılarını
kaçırmasının ihtimal dahilinde olduğunu unutmayın; Sorunuz önemli veya
önemsiz olsun, onları tekrar yakalamak için çekinmeyin.

Web tarayıcısı [Servo], HTTP kütüphanesi [hyper], kaynak formatlayıcı
[rustfmt], Unix kütüphane bağlayıcıları [nix] ve lint koleksiyonu [clippy]
gibi diğer Rust projeleri benzer giriş-seviyesi görevleri sağlar.

Rust [geniş test ortamına][test] sahip olmasına rağmen, test etmek için
daima daha fazla yöntem vardır. [E-needstest] etiketi düzeltilmiş fakat
henüz test edilmemiş problemleri içerir. Yeni bir projeyi anlamak ve
katkı sağlamak için test adımları yazmak harika bir yoldur.

Problemleri önceliklerine göre sıralamak için Rust'ın daima insanların
yardımlarına ihtiyacı vardır: yeni hatalar bulmak, test adımlarını minimize
etmek, etiketleri kullanmak, problemleri çözmek gibi. Etiketleri kullanmak
için GitHub yetkilerine ihtiyacınız olacaktır, ancak bu sorunu aşmak için
bir parça proje tecrübesi yeterli olacaktır. Bir [takım üyesine][team]
sorabilirsiniz.

Proje içerisinde kendine bir yol belirlediğinde veya belli bir alanda
bir kaç pull request gerçekleştirdiğinde, diğerlerinin pull request
işlemlerini gözden geçirebilirsin: Gözden geçirme yeteneği iyi olan
kişilerin sayısı azdır ve her zaman takdir edilirler. Bunun için herhangi
bir yetkiye ihtiyacınız yok &mdash; direk olarak sizinle ilgili olan
pull request hakkında nazik ve yapıcı bir şekilde yorum yapabilirsiniz.
Eğer davranış kuralları çerçevesinde iyi bir gözden geçirme yapmak
isterseniz, [bu rehberi][reviews] okuyabilirsiniz.

<!--
YAPILACAKLAR: haftalık elektronik posta önceliğini sıralamak
YAPILACAKLAR: @nrc alıştırma olmadan gözden geçirme işleminin iyi olmayacağını söylüyor.
-->

[@mentioning]: https://github.com/blog/821
[E-easy]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AE-easy
[E-mentor]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AE-easy+label%3AE-mentor
[E-needstest]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AE-needstest
[PR]: https://github.com/rust-lang/rust/pulls
[Servo]: https://github.com/servo/servo
[clippy]: https://github.com/Manishearth/rust-clippy
[hyper]: https://github.com/hyperium/hyper
[issue tracker]: https://github.com/rust-lang/rust/issues
[nix]: https://github.com/nix-rust/nix/
[pull]: https://github.com/rust-lang/rust/blob/master/CONTRIBUTING.md#pull-requests
[reviews]: http://blog.originate.com/blog/2014/09/29/effective-code-reviews/
[rustfmt]: https://github.com/rust-lang-nursery/rustfmt
[team]: team.html
[test]: https://github.com/rust-lang/rust-wiki-backup/blob/master/Note-testsuite.md
[triage]: https://github.com/rust-lang/rust/blob/master/CONTRIBUTING.md#issue-triage
