---
description: '詳細情報: once プラグマ'
title: once プラグマ
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.once
- once_CPP
helpviewer_keywords:
- once pragma
- pragmas, once
ms.assetid: c7517556-6403-4b16-8898-f2aa0a6f685f
ms.openlocfilehash: 3aa1e50173ef625d13ad9f36684aec3a1c512d2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333235"
---
# <a name="once-pragma"></a>once プラグマ

ソースコードファイルをコンパイルするときに、コンパイラがヘッダーファイルを1回だけインクルードすることを指定します。

## <a name="syntax"></a>構文

> **一度 #pragma**

## <a name="remarks"></a>解説

を使用すると `#pragma once` 、ビルド時間を短縮できます。これは、変換単位の最初のファイルの後にコンパイラが開かず、ファイルを再度読み取るため `#include` です。 これは、 *複数インクルードの最適化* と呼ばれます。 これは、 *インクルードガード* 表現に似ています。これは、プリプロセッサマクロ定義を使用して、ファイルの内容が複数インクルードされないようにします。 また、 *1 つの定義規則* に違反しないようにすることもできます。これは、すべてのテンプレート、型、関数、およびオブジェクトがコード内で定義を1つしか持たないという要件です。

次に例を示します。

```cpp
// header.h
#pragma once
// Code placed here is included only once per translation unit
```

新しいコードには `#pragma once` ディレクティブを使用することをお勧めします。これを使えば、プリプロセッサ シンボルによるグローバル名前空間のポリューションが発生しないためです。 これには、入力が少なく、混乱が少なく、 *シンボルの競合* を発生させることはできません。異なるヘッダーファイルで、ガード値と同じプリプロセッサシンボルが使用されていると、エラーが発生します。 これは C++ 標準の一部ではありませんが、いくつかの一般的なコンパイラによって移植に実装されています。

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

[プラグマ ディレクティブと __pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
