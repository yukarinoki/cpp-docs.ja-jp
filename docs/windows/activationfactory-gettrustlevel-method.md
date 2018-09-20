---
title: Activationfactory::gettrustlevel メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::GetTrustLevel
dev_langs:
- C++
helpviewer_keywords:
- GetTrustLevel method
ms.assetid: 31547ae6-d2ab-4039-923c-154d53fb1a8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eba02bea09784e3431b3697eb9ac9a47de978348
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424561"
---
# <a name="activationfactorygettrustlevel-method"></a>ActivationFactory::GetTrustLevel メソッド

オブジェクトの信頼レベルを取得、現在**ActivationFactory**をインスタンス化します。

## <a name="syntax"></a>構文

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

### <a name="parameters"></a>パラメーター

*trustLvl*<br/>
この操作が完了したら、信頼レベルのランタイム クラス、 **ActivationFactory**をインスタンス化します。

## <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、アサーション エラーが発生したと*trustLvl*に設定されている`FullTrust`します。

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[ActivationFactory クラス](../windows/activationfactory-class.md)