---
title: alloc_text プラグマ
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.alloc_text
- alloc_text_CPP
helpviewer_keywords:
- alloc_text pragma
- pragmas, alloc_text
ms.assetid: 1fd7be18-e4f7-4f70-b079-6326f72b871a
ms.openlocfilehash: c638c2026a493453aeb5aff00ba6273efb5f184e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219444"
---
# <a name="alloc_text-pragma"></a>alloc_text プラグマ

指定した関数定義が存在するコード セクションに名前を付けます。 このプラグマは、名前付き関数の関数宣言子と関数定義との間で指定する必要があります。

## <a name="syntax"></a>構文

> **#pragma alloc_text (** "*textsection*" **,** *function1* [**,** *function2* ...] **)**

## <a name="remarks"></a>解説

**Alloc_text**プラグマは、C++ のメンバー関数またはオーバーロードされた関数を処理しません。 これは、C リンケージ (つまり、 **extern "C"** リンケージ仕様で宣言された関数) で宣言された関数にのみ適用できます。 C++ リンケージを持つ関数でこのプラグマを使用しようとすると、コンパイラ エラーが生成されます。

を使用した関数のアドレス指定はサポートされて **`__based`** いないため、セクションの場所を指定するには、 **alloc_text**プラグマを使用する必要があります。 *Textsection*によって指定された名前は、二重引用符で囲む必要があります。

**Alloc_text**プラグマは、指定された関数の宣言の後、およびこれらの関数の定義の前に記述する必要があります。

**Alloc_text**プラグマで参照される関数は、プラグマと同じモジュールで定義する必要があります。 それ以外の場合、定義されていない関数が後で別のテキストセクションにコンパイルされると、エラーがキャッチされるか、またはキャッチされない可能性があります。 プログラムは正常に動作しますが、関数は目的のセクションでは割り当てられません。

**Alloc_text**に関するその他の制限事項は次のとおりです。

- 関数内では使用できません。

- 関数が宣言された後で、関数が定義される前に使用する必要があります。

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
