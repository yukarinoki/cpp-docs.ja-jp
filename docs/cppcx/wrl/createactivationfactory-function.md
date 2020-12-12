---
description: '詳細情報: CreateActivationFactory 関数'
title: CreateActivationFactory 関数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateActivationFactory
helpviewer_keywords:
- CreateActivationFactory function
ms.assetid: a1a53e04-6757-4faf-a4c8-ecf06e43b959
ms.openlocfilehash: 25f2181a00bb018361b05ea6570ebbadc6f7a975
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273108"
---
# <a name="createactivationfactory-function"></a>CreateActivationFactory 関数

Windows ランタイムによるアクティブ化が可能な、指定されたクラスのインスタンスを生成するファクトリを作成します。

## <a name="syntax"></a>構文

```cpp
template<typename Factory>
   inline HRESULT STDMETHODCALLTYPE CreateActivationFactory(
      _In_ unsigned int *flags,        _In_ const CreatorMap* entry,
      REFIID riid,
   _Outptr_ IUnknown **ppFactory) throw();
```

### <a name="parameters"></a>パラメーター

*flags*<br/>
1つ以上の [RuntimeClassType](runtimeclasstype-enumeration.md) 列挙値の組み合わせ。

*キー*<br/>
パラメーター *riid* に関する初期化および登録情報を格納する [CreatorMap](creatormap-structure.md)へのポインター。

*riid*<br/>
インターフェイス ID への参照。

*ppFactory*<br/>
この操作が正常に完了した場合は、アクティベーションファクトリへのポインター。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="remarks"></a>解説

テンプレートパラメーター *ファクトリ* がインターフェイスから派生していない場合、アサートエラーが生成され `IActivationFactory` ます。

## <a name="requirements"></a>要件

**ヘッダー:** resource.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft:: WRL:: Wrapper::D etails 名前空間](microsoft-wrl-wrappers-details-namespace.md)
