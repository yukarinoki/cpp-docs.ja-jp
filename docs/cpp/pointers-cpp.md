---
title: ポインター (C++)
ms.date: 11/19/2019
description: Microsoft C++ の生のポインターとスマート ポインターについて。
helpviewer_keywords:
- pointers (C++)
ms.assetid: 595387c5-8e58-4670-848f-344c7caf985e
ms.openlocfilehash: 485cee667fa288bff76fdeac7c9f229355c276d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371916"
---
# <a name="pointers-c"></a>ポインター (C++)

ポインターは、オブジェクトのメモリ アドレスを格納する変数です。 ポインタは C および C++ の両方で、主に 3 つの目的で広く使用されています。

- ヒープに新しいオブジェクトを割り当てるには、
- 関数を他の関数に渡す
- を使用して、配列やその他のデータ構造内の要素を反復処理します。

C スタイルのプログラミングでは、*生のポインター*はこれらすべてのシナリオに使用されます。 しかし、生のポインタは多くの深刻なプログラミングエラーの原因です。 したがって、パフォーマンス上の利点が大きく、オブジェクトを削除する*対象となる所有ポインター*がどのポインターであるかがあいまいさがない場合を除き、これらの使用は推奨しません。 モダン C++ には、オブジェクトを割り当てるための*スマート ポインター* 、データ構造体を走査するための*反復子*、関数を渡すための*ラムダ式*が用意されています。 生のポインタではなくこれらの言語およびライブラリ機能を使用することで、プログラムをより安全に、デバッグしやすく、理解し、保守しやすくなります。 詳細については、「[スマート ポインター](smart-pointers-modern-cpp.md)、[イテレータ](../standard-library/iterators.md)、ラム[ダ式](lambda-expressions-in-cpp.md)」を参照してください。

## <a name="in-this-section"></a>このセクションの内容

- [生ポインター](raw-pointers.md)
- [定数および揮発性のポインタ](const-and-volatile-pointers.md)
- [新規および削除演算子](new-and-delete-operators.md)
- [スマート ポインター](smart-pointers-modern-cpp.md)
- [方法: unique_ptrインスタンスを作成して使用する](how-to-create-and-use-unique-ptr-instances.md)
- [方法: shared_ptrインスタンスを作成して使用する](how-to-create-and-use-shared-ptr-instances.md)
- [方法: weak_ptrインスタンスを作成して使用する](how-to-create-and-use-weak-ptr-instances.md)
- [方法: CComPtr インスタンスと CComQIPtr インスタンスを作成して使用する](how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md)

## <a name="see-also"></a>関連項目

[Iterators](../standard-library/iterators.md)</br>
[ラムダ式](lambda-expressions-in-cpp.md)
