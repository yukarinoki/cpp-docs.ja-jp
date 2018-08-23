---
title: Module::unregisterwinrtobject メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::UnregisterWinRTObject
dev_langs:
- C++
helpviewer_keywords:
- UnregisterWinRTObject method
ms.assetid: 32334aa7-2293-40d2-9a89-4b02e2e31f3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 88cafb7796ba0dfd1e37902821872e860ddc4baf
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42592185"
---
# <a name="moduleunregisterwinrtobject-method"></a>Module::UnregisterWinRTObject メソッド

他のアプリケーションがそれらに接続できないように、1 つまたは複数の Windows ランタイム オブジェクトを登録解除します。

## <a name="syntax"></a>構文

```cpp
virtual HRESULT UnregisterWinRTObject(
   unsigned int,
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie
);
```

### <a name="parameters"></a>パラメーター

*Cookie*  
登録を取り消すことは、クラス オブジェクトを識別する値へのポインター。

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目
[Module クラス](../windows/module-class.md)