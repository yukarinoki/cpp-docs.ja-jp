---
title: CreateClassFactory 関数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateClassFactory
helpviewer_keywords:
- CreateClassFactory function
ms.assetid: 772d5d1b-8872-4745-81ca-521a39564713
ms.openlocfilehash: 0467a9a1341e29a61a3b32d999769b01385f641f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214059"
---
# <a name="createclassfactory-function"></a>CreateClassFactory 関数

指定されたクラスのインスタンスを生成するファクトリを作成します。

## <a name="syntax"></a>構文

```cpp
template<typename Factory>
inline HRESULT STDMETHODCALLTYPE CreateClassFactory(
   _In_ unsigned int *flags,
   _In_ const CreatorMap* entry,
   REFIID riid,
   _Outptr_ IUnknown **ppFactory
) throw();
```

### <a name="parameters"></a>パラメーター

*flags*<br/>
1つ以上の[RuntimeClassType](runtimeclasstype-enumeration.md)列挙値の組み合わせ。

*entry*<br/>
パラメーター *riid*に関する初期化および登録情報を格納する[CreatorMap](creatormap-structure.md)へのポインター。

*riid*<br/>
インターフェイス ID への参照。

*ppFactory*<br/>
この操作が正常に完了した場合は、クラスファクトリへのポインター。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="remarks"></a>解説

テンプレートパラメーター*ファクトリ*がインターフェイス `IClassFactory`から派生していない場合、assert エラーが生成されます。

## <a name="requirements"></a>必要条件

**ヘッダー:** resource.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>参照

[Microsoft::WRL::Wrappers::Details 名前空間](microsoft-wrl-wrappers-details-namespace.md)
