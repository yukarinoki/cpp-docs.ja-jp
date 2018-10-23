---
title: rename_search_namespace |Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- rename_search_namespace
dev_langs:
- C++
helpviewer_keywords:
- rename_search_namespace attribute
ms.assetid: 47c9d7fd-59dc-4c62-87a1-9011a0040167
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f0cc95851c4aa7127e690ec013b9d06d57f2730d
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808889"
---
# <a name="renamesearchnamespace"></a>rename_search_namespace

**C++ 固有の仕様**

同じ機能を持つ、 [rename_namespace](../preprocessor/rename-namespace.md)属性しますが、使用するタイプ ライブラリで使用されて、`#import`ディレクティブ、 [auto_search](../preprocessor/auto-search.md)属性。

## <a name="syntax"></a>構文

```
rename_search_namespace("NewName")
```

### <a name="parameters"></a>パラメーター

*NewName*<br/>
名前空間の新しい名前。

## <a name="remarks"></a>Remarks

**END C 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)