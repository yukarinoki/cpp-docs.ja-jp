---
title: サンプル コンテナーのメンバー
ms.date: 11/04/2016
helpviewer_keywords:
- container classes
ms.assetid: dc5a1998-a31b-4adf-b888-8abe5b87a4e0
ms.openlocfilehash: ea30810177d936248f836e7e4462739d8b5f393a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846265"
---
# <a name="sample-container-members"></a>サンプル コンテナーのメンバー

> [!NOTE]
> このトピックは、C++ 標準ライブラリで使用されるコンテナーの非機能例として、Microsoft C++ ドキュメントに記載されています。 詳細については、「[C++ 標準ライブラリ コンテナー](../standard-library/stl-containers.md)」を参照してください。

## <a name="reference"></a>リファレンス

## <a name="typedefs"></a>Typedefs

|名前|説明|
|-|-|
|[const_iterator](../standard-library/container-class-const-iterator.md)|被制御シーケンスの定数反復子として使用できるオブジェクトを表します。|
|[const_reference](../standard-library/container-class-const-reference.md)|被制御シーケンスの要素への定数参照として使用できるオブジェクトを表します。|
|[const_reverse_iterator](../standard-library/container-class-const-reverse-iterator.md)|被制御シーケンスの定数反転反復子として使用できるオブジェクトを表します。|
|[difference_type](../standard-library/container-class-difference-type.md)|被制御シーケンス内にある任意の 2 つの要素のアドレスの違いを表現できるオブジェクトを記述します。|
|[反](../standard-library/container-class-iterator.md)|被制御シーケンスの反復子として使用できるオブジェクトを表します。|
|[reference](../standard-library/container-class-reference.md)|被制御シーケンスの要素への参照として使用できるオブジェクトを表します。|
|[reverse_iterator](../standard-library/container-class-reverse-iterator.md)|被制御シーケンスの反転反復子として使用できるオブジェクトを表します。|
|[size_type](../standard-library/container-class-size-type.md)|すべての被制御シーケンスの長さを表現できるオブジェクトを表します。|
|[value_type](../standard-library/container-class-value-type.md)|テンプレートパラメーターのシノニムとして機能 `Ty` します。|

## <a name="member-functions"></a>メンバー関数

|名前|説明|
|-|-|
|[初め](../standard-library/container-class-begin.md)|シーケンスの最初の要素 (または空のシーケンスの末尾の次の位置) を指す反復子を返します。|
|[オフ](../standard-library/container-class-clear.md)|[erase](../standard-library/container-class-erase.md)( [begin](../standard-library/container-class-begin.md), [end](../standard-library/container-class-end.md)) を呼び出します。|
|[empty](../standard-library/container-class-empty.md)|**`true`** 空の被制御シーケンスに対してを返します。|
|[end](../standard-library/container-class-end.md)|シーケンスの末尾の次の位置を指す反復子を返します。|
|[erase](../standard-library/container-class-erase.md)|要素を消去します。|
|[max_size](../standard-library/container-class-max-size.md)|被制御シーケンスの長さにかかわらず一定時間で、オブジェクトが制御できる最長のシーケンスの長さを返します。|
|[rbegin](../standard-library/container-class-rbegin.md)|被制御シーケンスの末尾の次の位置を指す反転反復子を返し、反転シーケンスの先頭を指定します。|
|[rend](../standard-library/container-class-rend.md)|このメンバー関数は、シーケンスの最初の要素 (または空のシーケンスの末尾の次の位置) を指す反転反復子を返し、反転シーケンスの末尾を指定します。|
|[size](../standard-library/container-class-size.md)|被制御シーケンスの長さにかかわらず一定時間で、被制御シーケンスの長さを返します。|
|[スワップ](../standard-library/container-class-swap.md)
