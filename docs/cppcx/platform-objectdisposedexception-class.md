---
title: Platform::objectdisposedexception クラス |Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ObjectDisposedException
- VCCORLIB/Platform::ObjectDisposedException::ObjectDisposedException
dev_langs:
- C++
helpviewer_keywords:
- Platform::ObjectDisposedException
ms.assetid: 68506fe4-d09c-4407-999f-1e3edb261d41
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f0574885fb404572052fbf5066b522ed0208eba
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106926"
---
# <a name="platformobjectdisposedexception-class"></a>Platform::ObjectDisposedException クラス

破棄されたオブジェクトで操作が実行されるとスローされます。

## <a name="syntax"></a>構文

```cpp
public ref class ObjectDisposedException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Remarks

詳細については、「 [COMException](../cppcx/platform-comexception-class.md)」を参照してください。

### <a name="requirements"></a>要件

**クライアントがサポートされている最小:** Windows 8

**サポートされているサーバーの最小値:** Windows Server 2012

**名前空間:** Platform

**メタデータ:** platform.winmd

## <a name="see-also"></a>関連項目

[Platform::COMException クラス](../cppcx/platform-comexception-class.md)