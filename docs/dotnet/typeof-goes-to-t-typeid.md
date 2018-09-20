---
title: typeof が::typeid への移動 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- typeid operator
- __typeof keyword
- typeid keyword [C++]
ms.assetid: 6a0d35a7-7a1a-4070-b187-cff37cfdc205
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4433061fceef455685b6588c81c8c2e434253433
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374678"
---
# <a name="typeof-goes-to-ttypeid"></a>typeof から T::typeid への移行

`typeof` C++ が置き換わりましたされているは、マネージ拡張で使用される演算子、 `typeid` Visual C でキーワード。

マネージ拡張で、`__typeof()`演算子は、関連付けられている返します`Type*`マネージ型の名前が渡されるオブジェクトします。 例えば:

```
// Creates and initializes a new Array instance.
Array* myIntArray =
   Array::CreateInstance( __typeof(Int32), 5 );
```

新しい構文で`__typeof`の別の形式から置き換え`typeid`を返す、`Type^`マネージ型が指定されている場合。

```
// Creates and initializes a new Array instance.
Array^ myIntArray =
   Array::CreateInstance( Int32::typeid, 5 );
```

## <a name="see-also"></a>関連項目

[言語の変更の概要 (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)<br/>
[typeid](../windows/typeid-cpp-component-extensions.md)