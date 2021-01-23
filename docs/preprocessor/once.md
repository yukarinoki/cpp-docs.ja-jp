---
description: '詳細情報: 1 回 pragma'
title: ある時 pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.once
- once_CPP
helpviewer_keywords:
- once pragma
- pragma, once
no-loc:
- pragma
ms.openlocfilehash: 3edb5f88202ee783e587b1f886eddddf427f6133
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713481"
---
# <a name="once-no-locpragma"></a>`once` pragma

ソースコードファイルをコンパイルするときに、コンパイラがヘッダーファイルを1回だけインクルードすることを指定します。

## <a name="syntax"></a>構文

> **`#pragma once`**

## <a name="remarks"></a>解説

を使用すると `#pragma once` 、ビルド時間を短縮できます。これは、変換単位の最初のファイルの後にコンパイラが開かず、ファイルを再度読み取るため `#include` です。 これは、 *複数インクルードの最適化* と呼ばれます。 これは、 *インクルードガード* 表現に似ています。これは、プリプロセッサマクロ定義を使用して、ファイルの内容が複数インクルードされないようにします。 また、 *1 つの定義規則* に違反しないようにすることもできます。これは、すべてのテンプレート、型、関数、およびオブジェクトがコード内で定義を1つしか持たないという要件です。

例:

```cpp
// header.h
#pragma once
// Code placed here is included only once per translation unit
```

新しいコードには `#pragma once` ディレクティブを使用することをお勧めします。これを使えば、プリプロセッサ シンボルによるグローバル名前空間のポリューションが発生しないためです。 入力が少ないため、混乱が少なく、 *シンボルの競合* が発生することはありません。 シンボルの競合は、異なるヘッダーファイルでガード値と同じプリプロセッサシンボルが使用されている場合に発生するエラーです。 これは C++ 標準の一部ではありませんが、いくつかの一般的なコンパイラによって移植に実装されています。

インクルードガード表現とを `#pragma once` 同じファイル内に使用する利点はありません。 コンパイラはインクルードガード表現を認識し、 `#pragma once` 非コメントコードまたはプリプロセッサディレクティブが標準形式の表現の前または後にある場合、ディレクティブと同じ方法で複数インクルードの最適化を実装します。

```cpp
// header.h
// Demonstration of the #include guard idiom.
// Note that the defined symbol can be arbitrary.
#ifndef HEADER_H_     // equivalently, #if !defined HEADER_H_
#define HEADER_H_
// Code placed here is included only once per translation unit
#endif // HEADER_H_
```

ディレクティブを実装しないコンパイラにコードを移植する必要がある場合、 `#pragma once` 既存のコードとの一貫性を維持する場合、または複数インクルードの最適化が不可能な場合は、ガード表現を含めることをお勧めします。 複雑なプロジェクトでは、ファイルシステムの別名またはエイリアスインクルードパスを使用すると、コンパイラが正規のパスによって同一のインクルードファイルを識別できなくなる場合があります。

を使用しないようにする `#pragma once` か、複数回含めるように設計されたヘッダーファイルにガード表現を含めることは、その効果を制御するためにプリプロセッサシンボルを使用することに注意してください。 この設計の例については、ヘッダーファイルを参照してください \<assert.h> 。 また、インクルードファイルへの複数のパスを作成しないように、インクルードパスを慎重に管理してください。これにより、ガードとの両方に対して複数インクルードの最適化を無効にすることができ `#pragma once` ます。

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
