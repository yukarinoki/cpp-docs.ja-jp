---
title: Platform::classnotregisteredexception クラス |Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ClassNotRegisteredException::ClassNotRegisteredException
- VCCORLIB/Platform::ClassNotRegisteredException
dev_langs:
- C++
helpviewer_keywords:
- Platform::ClassNotRegisteredException
ms.assetid: 8f8871d8-51b9-46e8-902e-ae023c9f1de9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a41d7dab53c50d0583fdb48f62d078ee54251f32
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44108511"
---
# <a name="platformclassnotregisteredexception-class"></a>Platform::ClassNotRegisteredException クラス

COM クラスが登録されていないときにスローされます。

## <a name="syntax"></a>構文

```cpp
public ref class ClassNotRegisteredException : COMException,    IException,    IPrintable,    IEquatable
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