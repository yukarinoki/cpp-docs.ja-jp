---
description: '詳細情報: ActivationFactoryCallback 関数'
title: ActivationFactoryCallback 関数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::ActivationFactoryCallback
helpviewer_keywords:
- ActivationFactoryCallback function
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
ms.openlocfilehash: 9398b3f681e32c7a73b46de549ce7c41a3af6196
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204616"
---
# <a name="activationfactorycallback-function"></a>ActivationFactoryCallback 関数

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
inline HRESULT STDAPICALLTYPE ActivationFactoryCallback(
   HSTRING activationId,
   IActivationFactory **ppFactory
);
```

### <a name="parameters"></a>パラメーター

*activationId*<br/>
ランタイムクラス名を指定する文字列を処理します。

*ppFactory*<br/>
この操作が完了すると、パラメーター *activationId* に対応するアクティベーションファクトリ。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。 可能性のあるエラー Hresult は CLASS_E_CLASSNOTAVAILABLE および E_INVALIDARG です。

## <a name="remarks"></a>解説

指定されたアクティベーション ID のアクティベーションファクトリを取得します。

Windows ランタイムは、このコールバック関数を呼び出して、ランタイムクラス名によって指定されたオブジェクトを要求します。

## <a name="requirements"></a>要件

**ヘッダー:** resource.h

**名前空間:** Microsoft:: WRL::D etails

## <a name="see-also"></a>関連項目

[Microsoft:: WRL::D etails 名前空間](microsoft-wrl-details-namespace.md)
