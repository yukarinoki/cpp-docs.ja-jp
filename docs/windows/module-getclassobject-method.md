---
title: Module::getclassobject メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GetClassObject
dev_langs:
- C++
helpviewer_keywords:
- GetClassObject method
ms.assetid: 95b0de1b-f728-4f96-9f44-f6ea71ce56e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 90a1b527d12e581c42fc9519e56d453f845e0b63
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419721"
---
# <a name="modulegetclassobject-method"></a>Module::GetClassObject メソッド

クラス ファクトリのキャッシュを取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetClassObject(
   REFCLSID clsid,
   REFIID riid,
   _Deref_out_ void **ppv,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>パラメーター

*clsid*<br/>
クラスの id。

*riid*<br/>
要求したインターフェイス ID です。

*ppv*<br/>
返されるオブジェクトへのポインター。

*サーバー名*<br/>
いずれかで指定されているサーバー名、 `ActivatableClassWithFactory`、 `ActivatableClassWithFactoryEx`、または`ActivatableClass`マクロ; または**nullptr**を既定のサーバー名を取得します。

## <a name="return-value"></a>戻り値

## <a name="remarks"></a>Remarks

このメソッドは、Windows ランタイムではなく COM にのみ使用します。 このメソッドを公開のみ`IClassFactory`メソッド。

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Module クラス](../windows/module-class.md)