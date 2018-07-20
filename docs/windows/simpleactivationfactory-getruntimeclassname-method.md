---
title: Simpleactivationfactory::getruntimeclassname メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName
dev_langs:
- C++
ms.assetid: 3aa07487-9a42-46f8-8893-37ba6315e50b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e001d0269c21026bdd00abcdd4d257f11d601cf6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889034"
---
# <a name="simpleactivationfactorygetruntimeclassname-method"></a>SimpleActivationFactory::GetRuntimeClassName メソッド

によって指定されたクラスのインスタンスのランタイム クラス名を取得、`Base`クラス テンプレート パラメーター。

## <a name="syntax"></a>構文

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>パラメーター

*runtimeName*  
この操作の完了時、ランタイム クラス名。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="remarks"></a>コメント

場合&#95; &#95;WRL_STRICT&#95; &#95;は、定義されている、assert エラーが発生して、クラスが指定されている場合、`Base`から派生したクラス テンプレート パラメーターはありません[RuntimeClass](../windows/runtimeclass-class.md)、かで構成されていません、WinRt または WinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙値。

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[SimpleActivationFactory クラス](../windows/simpleactivationfactory-class.md)