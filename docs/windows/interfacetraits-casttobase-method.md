---
title: Interfacetraits::casttobase メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToBase
dev_langs:
- C++
helpviewer_keywords:
- CastToBase method
ms.assetid: 0591a017-0adf-4358-b946-eb0a307ce7f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 473656f25c4ba08e011bef8f938cea54bdc51d6d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424905"
---
# <a name="interfacetraitscasttobase-method"></a>InterfaceTraits::CastToBase メソッド

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template<typename T>
static __forceinline Base* CastToBase(
   _In_ T* ptr
);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
パラメーターの型*ptr*します。

*ptr*<br/>
型へのポインター *T*します。

## <a name="return-value"></a>戻り値

ポインター`Base`します。

## <a name="remarks"></a>Remarks

指定したポインターへのポインターにキャスト`Base`します。

詳細については`Base`、パブリック Typedef」セクションを参照してください。 [InterfaceTraits 構造体](../windows/interfacetraits-structure.md)します。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[InterfaceTraits 構造体](../windows/interfacetraits-structure.md)<br/>
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)