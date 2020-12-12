---
description: '詳細情報: Platform:: AccessDeniedException クラス'
title: Platform::AccessDeniedException クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::AccessDeniedException
- VCCORLIB/Platform::AccessDeniedException::AccessDeniedException
helpviewer_keywords:
- Platform::AccessDeniedException
ms.assetid: 6ae2155b-7b16-4587-8d2d-da05eab4c7e9
ms.openlocfilehash: 2dd1e543093000521bceb0abed128a1dac27a6e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276791"
---
# <a name="platformaccessdeniedexception-class"></a>Platform::AccessDeniedException クラス

リソースや機能へのアクセスが拒否されるとスローされます。

## <a name="syntax"></a>構文

```cpp
public ref class AccessDeniedException : COMException,    IException,    IPrintable,   IEquatable
```

### <a name="remarks"></a>解説

この例外にヒットした場合は、適切な機能を要求したこと、およびアプリのパッケージ マニフェストで必要な宣言を行ったことを確認します。 詳細については、「 [COMException](../cppcx/platform-comexception-class.md) 」クラスを参照してください。

### <a name="requirements"></a>要件

**サポートされている最低限のクライアント:** Windows 8

**サポートされる最小サーバー:** Windows Server 2012

**名前空間:** Platform

**メタデータ:** platform. winmd

## <a name="see-also"></a>関連項目

[Platform:: COMException クラス](../cppcx/platform-comexception-class.md)
