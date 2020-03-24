---
title: CreateActivationFactory 関数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateActivationFactory
helpviewer_keywords:
- CreateActivationFactory function
ms.assetid: a1a53e04-6757-4faf-a4c8-ecf06e43b959
ms.openlocfilehash: ab03b15a968c6aba3fa6df8c975fb98e873f8e23
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214072"
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
1つ以上の[RuntimeClassType](runtimeclasstype-enumeration.md)列挙値の組み合わせ。

*entry*<br/>
パラメーター *riid*に関する初期化および登録情報を格納する[CreatorMap](creatormap-structure.md)へのポインター。

*riid*<br/>
インターフェイス ID への参照。

*ppFactory*<br/>
この操作が正常に完了した場合は、アクティベーションファクトリへのポインター。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="remarks"></a>解説

テンプレートパラメーター*ファクトリ*がインターフェイス `IActivationFactory`から派生していない場合、assert エラーが生成されます。

## <a name="requirements"></a>必要条件

**ヘッダー:** resource.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>参照

[Microsoft::WRL::Wrappers::Details 名前空間](microsoft-wrl-wrappers-details-namespace.md)
