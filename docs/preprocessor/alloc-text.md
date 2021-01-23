---
description: pragmaMicrosoft C/c + + での alloc_text ディレクティブの詳細については、こちらを参照してください。
title: alloc_text pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.alloc_text
- alloc_text_CPP
helpviewer_keywords:
- alloc_text pragma
- pragma, alloc_text
no-loc:
- pragma
ms.openlocfilehash: f20cbf90952c6ac5793c5bdf4d2ef1c533be2126
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713130"
---
# <a name="alloc_text-no-locpragma"></a>`alloc_text` pragma

指定された関数定義が配置されるコードセクションに名前を付けます。 は、 pragma 関数宣言子と名前付き関数の関数定義の間で発生する必要があります。

## <a name="syntax"></a>構文

> **`#pragma alloc_text(`** "*テキストセクション*" **`,`** *function_1* [ **`,`** *function_2* ...] **`)`**

## <a name="remarks"></a>解説

は、 **`alloc_text`** pragma C++ のメンバー関数またはオーバーロードされた関数を処理しません。 これは、C リンケージで宣言された関数、つまりリンケージ仕様で宣言された関数にのみ適用 **`extern "C"`** できます。 C++ リンケージを持つ関数でこれを使用しようとすると pragma 、コンパイラエラーが生成されます。

を使用した関数のアドレス指定は **`__based`** サポートされていないため、セクションの場所を指定するにはを使用する必要があり **`alloc_text`** pragma ます。 *テキストセクション* で指定された名前は、二重引用符で囲む必要があります。

は、 **`alloc_text`** pragma 指定された関数の宣言の後、およびこれらの関数の定義の前に記述する必要があります。

で参照される関数は **`alloc_text`** pragma 、と同じモジュールで定義する必要があり pragma ます。 それ以外の場合、定義されていない関数が後で別のテキストセクションにコンパイルされると、エラーがキャッチされるか、またはキャッチされない可能性があります。 通常、プログラムは正常に実行されますが、この関数は目的のセクションには割り当てられません。

に関するその他の制限事項は次のとおり **`alloc_text`** です。

- 関数内では使用できません。

- 関数が宣言された後で、関数が定義される前に使用する必要があります。

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
