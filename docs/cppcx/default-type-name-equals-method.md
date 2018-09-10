---
title: '既定:: (type_name)::equals メソッド |Microsoft Docs'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::Object::Equals
dev_langs:
- C++
ms.assetid: 4450f835-06fc-4758-8d0a-72cf00007873
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 127f5ee876790fa3cfb8a052c2db6c41cc00f332
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44109020"
---
# <a name="defaulttypenameequals-method"></a>default::(type_name)::Equals メソッド

指定したオブジェクトが、現在のオブジェクトと等しいかどうかを判断します。

## <a name="syntax"></a>構文

```cpp
bool Equals(
    Object^ obj
)
```

### <a name="parameters"></a>パラメーター

*obj*<br/>
比較対象のオブジェクト。

### <a name="return-value"></a>戻り値

オブジェクトが等しい場合は`true` 。それ以外の場合は `false`。

### <a name="requirements"></a>要件

**クライアントがサポートされている最小:** Windows 8

**サポートされているサーバーの最小値:** Windows Server 2012

**名前空間:** 既定

**ヘッダー:** vccorlib.h

## <a name="see-also"></a>関連項目

[default 名前空間](../cppcx/default-namespace.md)