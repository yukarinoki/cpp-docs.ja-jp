---
title: サンプル コンテナーのメンバー | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- container classes
ms.assetid: dc5a1998-a31b-4adf-b888-8abe5b87a4e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33a251b2b9bf9b010367a88a4c9f566a73acb544
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956782"
---
# <a name="sample-container-members"></a>サンプル コンテナーのメンバー

> [!NOTE]
> このトピックは、C++ 標準ライブラリで使用されるコンテナーの例 (実際には機能しない) として、Visual C++ ドキュメントに含まれています。 詳細については、「[C++ Standard Library Containers (C++ 標準ライブラリ コンテナ―)](../standard-library/stl-containers.md)」をご覧ください。

## <a name="reference"></a>参照

## <a name="typedefs"></a>Typedefs

|||
|-|-|
|[const_iterator](../standard-library/container-class-const-iterator.md)|被制御シーケンスの定数反復子として使用できるオブジェクトを表します。|
|[const_reference](../standard-library/container-class-const-reference.md)|被制御シーケンスの要素への定数参照として使用できるオブジェクトを表します。|
|[const_reverse_iterator](../standard-library/container-class-const-reverse-iterator.md)|被制御シーケンスの定数反転反復子として使用できるオブジェクトを表します。|
|[difference_type](../standard-library/container-class-difference-type.md)|被制御シーケンス内にある任意の 2 つの要素のアドレスの違いを表現できるオブジェクトを記述します。|
|[iterator](../standard-library/container-class-iterator.md)|被制御シーケンスの反復子として使用できるオブジェクトを表します。|
|[reference](../standard-library/container-class-reference.md)|被制御シーケンスの要素への参照として使用できるオブジェクトを表します。|
|[reverse_iterator](../standard-library/container-class-reverse-iterator.md)|被制御シーケンスの反転反復子として使用できるオブジェクトを表します。|
|[size_type](../standard-library/container-class-size-type.md)|すべての被制御シーケンスの長さを表現できるオブジェクトを表します。|
|[value_type](../standard-library/container-class-value-type.md)|テンプレート パラメーターのシノニムの動作`Ty`します。|

## <a name="member-functions"></a>メンバー関数

|||
|-|-|
|[begin](../standard-library/container-class-begin.md)|シーケンスの最初の要素 (または空のシーケンスの末尾の次の位置) を指す反復子を返します。|
|[clear](../standard-library/container-class-clear.md)|[erase](../standard-library/container-class-erase.md)( [begin](../standard-library/container-class-begin.md), [end](../standard-library/container-class-end.md)) を呼び出します。|
|[empty](../standard-library/container-class-empty.md)|被制御シーケンスが空の場合に **true** を返します。|
|[end](../standard-library/container-class-end.md)|シーケンスの末尾の次の位置を指す反復子を返します。|
|[erase](../standard-library/container-class-erase.md)|要素を消去します。|
|[max_size](../standard-library/container-class-max-size.md)|被制御シーケンスの長さにかかわらず一定時間で、オブジェクトが制御できる最長のシーケンスの長さを返します。|
|[rbegin](../standard-library/container-class-rbegin.md)|被制御シーケンスの末尾の次の位置を指す反転反復子を返し、反転シーケンスの先頭を指定します。|
|[rend](../standard-library/container-class-rend.md)|このメンバー関数は、シーケンスの最初の要素 (または空のシーケンスの末尾の次の位置) を指す反転反復子を返し、反転シーケンスの末尾を指定します。|
|[size](../standard-library/container-class-size.md)|被制御シーケンスの長さにかかわらず一定時間で、被制御シーケンスの長さを返します。|
|[swap](../standard-library/container-class-swap.md)
