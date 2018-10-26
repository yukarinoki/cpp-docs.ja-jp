---
title: no_namespace |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_namespace
dev_langs:
- C++
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e84cfad5a11c0d691c56e6e7ddcca17ea87e3f02
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50082922"
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

**END C 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)