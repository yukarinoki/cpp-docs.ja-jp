---
title: iostreams の規則
ms.date: 11/04/2016
helpviewer_keywords:
- iostream header
- C++ Standard Library, iostreams
ms.assetid: 9fe5ded0-37a1-48d1-9671-c81ffc4760ad
ms.openlocfilehash: 7bfc497ec7c55a611d29cd62d076c0ac2e9b6e9f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845459"
---
# <a name="iostreams-conventions"></a>iostreams の規則

iostreams のヘッダーは、テキストとエンコードされた形式間の変換、および外部ファイルへの入力と出力の間の変換をサポートします。

[\<fstream>](../standard-library/fstream.md)\
[\<iomanip>](../standard-library/iomanip.md)\
[\<ios>](../standard-library/ios.md)\
[\<iosfwd>](../standard-library/iosfwd.md)\
[\<iostream>](../standard-library/iostream.md)\
[\<istream>](../standard-library/istream.md)\
[\<ostream>](../standard-library/ostream.md)\
[\<sstream>](../standard-library/sstream.md)\
[\<streambuf>](../standard-library/streambuf.md)\
[\<strstream>](../standard-library/strstream.md)

Iostreams を使用する最も簡単な方法は、ヘッダーを含めることだけです [\<iostream>](../standard-library/iostream.md) 。 これにより、[cin](../standard-library/iostream.md#cin) または [wcin](../standard-library/iostream.md#wcin) から値を抽出して標準の入力を読み取ることができます。 この操作を行うための規則は、クラスの説明「[basic_istream クラス](../standard-library/basic-istream-class.md)」で概要が示されています。 値を [cout](../standard-library/iostream.md#cout) または [wcout](../standard-library/iostream.md#wcout) に挿入して、標準出力を書き込むこともできます。 この操作を行うための規則は、クラスの説明「[basic_ostream クラス](../standard-library/basic-ostream-class.md)」で概要が示されています。 抽出と挿入の両方に共通するコントロールの書式設定は、クラス [basic_ios クラス](../standard-library/basic-ios-class.md) によって管理されています。 オブジェクトの抽出および挿入という名目でのこの書式設定情報の操作は、少数のマニピュレ―ターのみが行うことができます。

で宣言されたクラスを使用して、名前で開くファイルに対して同じ iostreams 操作を実行でき [\<fstream>](../standard-library/fstream.md) ます。 Iostreams とクラス [Basic_string クラス](../standard-library/basic-string-class.md)のオブジェクトを変換するには、で宣言されたクラスを使用し [\<sstream>](../standard-library/sstream.md) ます。 C 文字列を使用して同じ操作を行うには、で宣言されたクラスを使用し [\<strstream>](../standard-library/strstream.md) ます。

残りのヘッダーは、通常は iostreams クラスの上級ユーザーのみに直接利益があるサポート サービスを提供するものです。

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
