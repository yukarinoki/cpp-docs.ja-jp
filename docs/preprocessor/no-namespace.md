---
title: no_namespace
ms.date: 11/04/2016
f1_keywords:
- no_namespace
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
ms.openlocfilehash: f6bd60de02bf0166d5cf0b0cd1bc1de56ceda5bf
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59028718"
---
# <a name="nonamespace"></a>no_namespace
**C++ 固有の仕様**

名前空間名がコンパイラによって生成されないことを指定します。

## <a name="syntax"></a>構文

```
no_namespace
```

## <a name="remarks"></a>Remarks

`#import` ヘッダー ファイルのタイプ ライブラリの内容は、通常、特定の名前空間で定義されます。 名前空間の名前がで指定された、`library`元の IDL ファイルのステートメント。 場合、 **no_namespace**属性を指定し、この名前空間は、コンパイラによって生成されません。

別の名前空間の名前を使用する場合を使用し、 [rename_namespace](../preprocessor/rename-namespace.md)属性の代わりにします。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)