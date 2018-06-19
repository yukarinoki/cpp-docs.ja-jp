---
title: Platform::recreateexception メソッド |Microsoft ドキュメント
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0472d74be21048aeaf25ca92dbb5c1e98ca0ca90
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33087830"
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

