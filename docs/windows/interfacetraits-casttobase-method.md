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
ms.openlocfilehash: 55a4d7487be5b3565ba3945630cab4388f287a68
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611825"
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

*T*  
パラメーターの型*ptr*します。

*ptr*  
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

[InterfaceTraits 構造体](../windows/interfacetraits-structure.md)  
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)