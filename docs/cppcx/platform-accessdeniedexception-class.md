---
title: Platform::accessdeniedexception クラス |Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::AccessDeniedException
- VCCORLIB/Platform::AccessDeniedException::AccessDeniedException
dev_langs:
- C++
helpviewer_keywords:
- Platform::AccessDeniedException
ms.assetid: 6ae2155b-7b16-4587-8d2d-da05eab4c7e9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c87cdc55359fbdd4855a062a3b1b56384c3be574
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44104187"
---
# <a name="platformaccessdeniedexception-class"></a>Platform::AccessDeniedException クラス

リソースや機能へのアクセスが拒否されるとスローされます。

## <a name="syntax"></a>構文

```cpp
public ref class AccessDeniedException : COMException,    IException,    IPrintable,   IEquatable
```

### <a name="remarks"></a>Remarks

この例外にヒットした場合は、適切な機能を要求したこと、およびアプリのパッケージ マニフェストで必要な宣言を行ったことを確認します。 詳細については、「 [COMException](../cppcx/platform-comexception-class.md) 」クラスを参照してください。

### <a name="requirements"></a>要件

**クライアントがサポートされている最小:** Windows 8

**サポートされているサーバーの最小値:** Windows Server 2012

**名前空間:** Platform

**メタデータ:** platform.winmd

## <a name="see-also"></a>関連項目

[Platform::COMException クラス](../cppcx/platform-comexception-class.md)