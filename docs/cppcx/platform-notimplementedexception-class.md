---
title: Platform::NotImplementedException クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::NotImplementedException
- VCCORLIB/Platform::NotImplementedException::NotImplementedException
helpviewer_keywords:
- Platform::NotImplementedException
ms.assetid: 6da26cc2-dde8-4aea-aa85-67aac55cf97b
ms.openlocfilehash: 26e8900a10b25507f5091d9cc1f724c73ece7dfd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467588"
---
# <a name="platformnotimplementedexception-class"></a>Platform::NotImplementedException クラス

インターフェイス メンバーが派生型で実装されていない場合にスローされます。

## <a name="syntax"></a>構文

```cpp
public ref class NotImplementedException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Remarks

詳細については、 [COMException](../cppcx/platform-comexception-class.md) クラスを参照してください。

### <a name="requirements"></a>必要条件

**クライアントがサポートされている最小:** Windows 8

**サポートされているサーバーの最小値:** Windows Server 2012

**名前空間:** Platform

**メタデータ:** platform.winmd

## <a name="see-also"></a>関連項目

[Platform::COMException クラス](../cppcx/platform-comexception-class.md)