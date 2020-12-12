---
description: '詳細情報: Platform:: ReCreateException メソッド'
title: 'Platform:: RecreateException メソッド'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Exception
helpviewer_keywords:
- Platform::Exception Class
ms.assetid: fa73d1ab-86e4-4d26-a7d9-81938c1c7e77
ms.openlocfilehash: 273f60055e4cf5a940558ba5dcaa4aa6a7c70bca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308056"
---
# <a name="platformrecreateexception-method"></a>Platform::ReCreateException メソッド

これは内部でのみ使用されるメソッドであり、ユーザー コードには使用されません。 代わりに、Exception::CreateException メソッドを使用してください。

## <a name="syntax"></a>構文

```cpp
static Exception^ ReCreateException(int hr)
```

### <a name="parameters"></a>パラメーター

*時間*

### <a name="property-valuereturn-value"></a>プロパティ値/戻り値

指定された HRESULT に基づいて新しい Platform::Exception^ を返します。
