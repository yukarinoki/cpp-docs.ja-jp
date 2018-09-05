---
title: Platform::recreateexception メソッド |Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Exception
dev_langs:
- C++
helpviewer_keywords:
- Platform::Exception Class
ms.assetid: fa73d1ab-86e4-4d26-a7d9-81938c1c7e77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7dc789ce0eb723410e5c62505183d5d3449d95c5
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43754697"
---
# <a name="platformrecreateexception-method"></a>Platform::ReCreateException メソッド
これは内部でのみ使用されるメソッドであり、ユーザー コードには使用されません。 Exception::createexception メソッドを代わりに使用します。

## <a name="syntax"></a>構文

```cpp
static Exception^ ReCreateException(int hr)
```

### <a name="parameters"></a>パラメーター
`hr`

### <a name="property-valuereturn-value"></a>プロパティ値/戻り値

指定された HRESULT に基づいて新しい Platform::Exception^ を返します。

