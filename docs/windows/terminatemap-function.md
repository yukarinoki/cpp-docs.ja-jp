---
title: TerminateMap 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
dev_langs:
- C++
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f844d63bc04deb4294203f04aef30db48f195fd9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438068"
---
# <a name="terminatemap-function"></a>TerminateMap 関数

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
inline bool TerminateMap(
   _In_ ModuleBase *module,
   _In_opt_z_ const wchar_t *serverName,
    bool forceTerminate) throw()  
```

### <a name="parameters"></a>パラメーター

*モジュール*<br/>
A[モジュール](../windows/module-class.md)します。

*サーバー名*<br/>
パラメーターで指定されたモジュールでクラス ファクトリのサブセットの名前*モジュール*します。

*forceTerminate*<br/>
**true**クラスを終了するに関係なく、ファクトリがアクティブです。**false**クラス ファクトリを終了しない場合は、ファクトリがアクティブにします。

## <a name="return-value"></a>戻り値

**true**クラス ファクトリをすべてが終了した。 それ以外の場合**false**します。

## <a name="remarks"></a>Remarks

指定されたモジュールでクラス ファクトリをシャット ダウンします。

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)