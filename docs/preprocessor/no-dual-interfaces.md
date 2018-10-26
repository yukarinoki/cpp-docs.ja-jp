---
title: no_dual_interfaces |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_dual_interfaces
dev_langs:
- C++
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6dcf63933a54983fcf98e35acce533670dc74ed4
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50070960"
---
# <a name="nodualinterfaces"></a>no_dual_interfaces
**C++ 固有の仕様**

コンパイラがデュアル インターフェイス メソッドのラッパー関数を生成する方法を変更します。

## <a name="syntax"></a>構文

```
no_dual_interfaces
```

## <a name="remarks"></a>Remarks

通常、ラッパーは、そのインターフェイスの仮想関数テーブルからメソッドを呼び出します。 **No_dual_interfaces**、ラッパーを呼び出す代わりに`IDispatch::Invoke`メソッドを呼び出します。

**END C 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)