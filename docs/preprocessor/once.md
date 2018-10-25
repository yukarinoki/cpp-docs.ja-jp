---
title: 後 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.once
- once_CPP
dev_langs:
- C++
helpviewer_keywords:
- once pragma
- pragmas, once
ms.assetid: c7517556-6403-4b16-8898-f2aa0a6f685f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 14b66b2305e90c0e36ed17d3c325f145ff850704
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50056023"
---
# <a name="once"></a>once
ソース コード ファイルをコンパイルする際、コンパイラによってファイルが 1 回だけ取り込まれる (開かれる) ようにします。

## <a name="syntax"></a>構文

```
#pragma once
```

## <a name="remarks"></a>Remarks

使用`#pragma once`コンパイラが開き、いない最初の後に、ファイルを読み取ると、ビルド時間を短縮できます`#include`の翻訳単位内のファイル。 呼ばれる*複数インクルードの最適化*します。 同様の効果がある、`#include guard`表現形式は、プリプロセッサ マクロの定義を使用して、ファイルの内容の複数のインクルードされないようにします。 これは、違反を防ぐためにも役立ちます、*単一定義規則*: 要件のすべてのテンプレート、型、関数、およびオブジェクトに、コードにある複数の定義があること。

例えば:

```
// header.h
#pragma once
// Code placed here is included only once per translation unit
```

新しいコードには `#pragma once` ディレクティブを使用することをお勧めします。これを使えば、プリプロセッサ シンボルによるグローバル名前空間のポリューションが発生しないためです。 またこのディレクティブは、必要な入力量や無駄も少なく、シンボルの競合の原因にもなりません。シンボルの競合とは、異なるヘッダー ファイルで同じプリプロセッサ シンボルがガード値として使用されたときに発生するエラーです。 これは C++ の標準の一部ではありませんが、いくつかの一般的なコンパイラにより移植可能な方法で実装されます。

同じファイルで #include guard 表現形式と `#pragma once` の両方を使用する利点はありません。 コメントではないコードまたはプリプロセッサ ディレクティブが標準的な表現形式の前後にくる場合、`#pragma once` ディレティブと同様の方法で、コンパイラにより #include guard 表現形式が認識され、複数インクルードの最適化が実装されます。

```
// header.h
// Demonstration of the #include guard idiom.
// Note that the defined symbol can be arbitrary.
#ifndef HEADER_H_     // equivalently, #if !defined HEADER_H_
#define HEADER_H_
// Code placed here is included only once per translation unit
#endif // HEADER_H_
```

お勧め、`#include guard`表現形式と、コードを実装していないコンパイラに移植する必要があります、`#pragma once`ディレクティブは、既存のコードとの一貫性を維持する場合や、複数インクルードの最適化が不可能。 これは、ファイル システムの別名または別名が設定されたインクルード パスにより、コンパイラが正規のパスを基準に同じインクルード ファイルを識別できなくなるような複雑なプロジェクトで発生する場合があります。

使用しないように注意する`#pragma once`または`#include guard`プリプロセッサ シンボルを使用して、その影響を制御する、複数回含まれるよう設計されているヘッダー ファイル内の表現形式です。 この設計の例は、次を参照してください。、 \<assert.h > ヘッダー ファイル。 管理をインクルード パスを無にインクルード ファイルは、複数のパスを作成しないようにする、複数インクルードの両方の最適化`#include guard`s と`#pragma once`します。

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)