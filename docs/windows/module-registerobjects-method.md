---
title: Module::registerobjects メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::RegisterObjects
dev_langs:
- C++
helpviewer_keywords:
- RegisterObjects method
ms.assetid: db4077b7-068d-4534-aaa5-41b5444ccb49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d332d59ed821e433e0ec1ba025f882b4339ad69a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440902"
---
# <a name="moduleregisterobjects-method"></a>Module::RegisterObjects メソッド

他のアプリケーションがそれらに接続できるように、COM または Windows ランタイムのオブジェクトを登録します。

## <a name="syntax"></a>構文

```cpp
HRESULT RegisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>パラメーター

*モジュール*<br/>
COM または Windows ランタイム オブジェクトの配列。

*サーバー名*<br/>
オブジェクトを作成したサーバーの名前です。

## <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、理由を示す HRESULT 操作に失敗しました。

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Module クラス](../windows/module-class.md)