---
title: Platform::outofmemoryexception クラス |Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::OutOfMemoryException
- VCCORLIB/Platform::OutOfMemoryException::OutOfMemoryException
dev_langs:
- C++
helpviewer_keywords:
- Platform::OutOfMemoryException
ms.assetid: 49c19f6b-f66c-4448-b861-91dcbf32de2c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 32061f76462b089a649d89dccd8c76f7a0d722f0
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44109759"
---
# <a name="platformoutofmemoryexception-class"></a>Platform::OutOfMemoryException クラス

メモリが不足して操作を完了できないときにスローされます。

## <a name="syntax"></a>構文

```cpp
public ref class OutOfMemoryException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Remarks

詳細については、 [COMException](../cppcx/platform-comexception-class.md) クラスを参照してください。

### <a name="requirements"></a>要件

**クライアントがサポートされている最小:** Windows 8

**サポートされているサーバーの最小値:** Windows Server 2012

**名前空間:** Platform

**メタデータ:** platform.winmd

## <a name="see-also"></a>関連項目

[Platform::COMException クラス](../cppcx/platform-comexception-class.md)