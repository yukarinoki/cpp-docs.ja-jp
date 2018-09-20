---
title: Module::unregisterobjects メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::UnregisterObjects
dev_langs:
- C++
helpviewer_keywords:
- UnregisterObjects method
ms.assetid: 3d8119a7-991d-45e9-b8c5-ed36c0be0332
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 87fb8ece3e1897a3ba460403d273bd649784ad44
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400435"
---
# <a name="moduleunregisterobjects-method"></a>Module::UnregisterObjects メソッド

他のアプリケーションがそれらに接続できないように、指定したモジュール内のオブジェクトを登録解除します。

## <a name="syntax"></a>構文

```cpp
HRESULT UnregisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>パラメーター

*モジュール*<br/>
モジュールへのポインター。

*サーバー名*<br/>
この操作によって影響を受けるオブジェクトのサブセットを指定する修飾名。

## <a name="return-value"></a>戻り値

この操作が成功した場合は s_ok を返します。それ以外の場合、エラー理由を示す HRESULT がこの操作に失敗しました。

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Module クラス](../windows/module-class.md)