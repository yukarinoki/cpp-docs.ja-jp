---
title: Weakreference::resolve メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::Resolve
dev_langs:
- C++
helpviewer_keywords:
- Resolve method
ms.assetid: fc65a4b7-48a0-4d64-a793-37f566fdd8e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1e0873b366c84e89b23ddbaa6c64f6b484f921e0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446336"
---
# <a name="weakreferenceresolve-method"></a>WeakReference::Resolve メソッド

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
STDMETHOD(Resolve)  
   (REFIID riid,
   _Deref_out_opt_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
インターフェイス ID。

*ppvObject*<br/>
この操作が完了するとは、強力な参照カウントが 0 以外の場合は、現在の強い参照のコピーします。

## <a name="return-value"></a>戻り値

- この操作が成功し、強い参照カウントがゼロの場合は s_ok を返します。 *PpvObject*にパラメーターが設定されている**nullptr**します。

- この操作が成功し、強力な参照カウントが 0 以外の場合は s_ok を返します。 *PpvObject*パラメーターが強い参照に設定します。

- それ以外の場合、理由を示す HRESULT をこの操作に失敗しました。

## <a name="remarks"></a>Remarks

強力な参照カウントが 0 以外の場合、現在の強い参照値に指定されたポインターを設定します。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[WeakReference Class1](../windows/weakreference-class1.md)<br/>
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)