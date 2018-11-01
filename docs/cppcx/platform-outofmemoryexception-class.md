---
title: Platform::OutOfMemoryException クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::OutOfMemoryException
- VCCORLIB/Platform::OutOfMemoryException::OutOfMemoryException
helpviewer_keywords:
- Platform::OutOfMemoryException
ms.assetid: 49c19f6b-f66c-4448-b861-91dcbf32de2c
ms.openlocfilehash: bf13e1589f651b7791fe67f6061b06b1a0bd897f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478183"
---
# <a name="platformoutofmemoryexception-class"></a>Platform::OutOfMemoryException クラス

メモリが不足して操作を完了できないときにスローされます。

## <a name="syntax"></a>構文

```cpp
public ref class OutOfMemoryException : COMException,    IException,    IPrintable,    IEquatable
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