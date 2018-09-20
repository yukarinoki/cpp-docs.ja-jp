---
title: Interfacetraits::cancastto メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: 275847cb-69ea-42bf-910f-05ba6ef8b48d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 705b495e3f6d626a742fd1a63989c8cc658446a4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379666"
---
# <a name="interfacetraitscancastto-method"></a>InterfaceTraits::CanCastTo メソッド

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template<typename T>
static __forceinline bool CanCastTo(
   _In_ T* ptr,
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>パラメーター

*ptr*<br/>
型へのポインターの名前。

*riid*<br/>
インターフェイス ID`Base`します。

*ppv*<br/>
この操作が成功すると場合、 *ppv*で指定されたインターフェイスを指す`Base`します。 それ以外の場合、 *ppv*に設定されている**nullptr**します。

## <a name="return-value"></a>戻り値

**true**この操作が成功した場合と*ptr*へのポインターにキャスト`Base`、それ以外の**false**します。

## <a name="remarks"></a>Remarks

指定したポインターへのポインターにキャストできるかどうかを示す`Base`します。

詳細については`Base`を参照してください、**パブリック Typedef**セクション[InterfaceTraits 構造体](../windows/interfacetraits-structure.md)します。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[InterfaceTraits 構造体](../windows/interfacetraits-structure.md)<br/>
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)