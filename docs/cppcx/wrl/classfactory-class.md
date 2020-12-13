---
description: '詳細情報: ClassFactory クラス'
title: ClassFactory クラス
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory
- module/Microsoft::WRL::ClassFactory::AddRef
- module/Microsoft::WRL::ClassFactory::ClassFactory
- module/Microsoft::WRL::ClassFactory::LockServer
- module/Microsoft::WRL::ClassFactory::QueryInterface
- module/Microsoft::WRL::ClassFactory::Release
helpviewer_keywords:
- Microsoft::WRL::ClassFactory class
- Microsoft::WRL::ClassFactory::AddRef method
- Microsoft::WRL::ClassFactory::ClassFactory, constructor
- Microsoft::WRL::ClassFactory::LockServer method
- Microsoft::WRL::ClassFactory::QueryInterface method
- Microsoft::WRL::ClassFactory::Release method
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
ms.openlocfilehash: e6503cba1060c432b2cb85020799b83f0ee16c6d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135305"
---
# <a name="classfactory-class"></a>ClassFactory クラス

`IClassFactory` インターフェイスの基本機能を実装します。

## <a name="syntax"></a>構文

```cpp
template <
    typename I0 = Details::Nil,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil
>
class ClassFactory :
    public Details::RuntimeClass<
        typename Details::InterfaceListHelper<
            IClassFactory,
            I0,
            I1,
            I2,
            Details::Nil
        >::TypeT,
        RuntimeClassFlags<ClassicCom | InhibitWeakReference>,
        false
    >;
```

### <a name="parameters"></a>パラメーター

*I0*<br/>
取り出しインターフェイス。

*I1*<br/>
最初のインターフェイス。

*I2*<br/>
2番目のインターフェイス。

## <a name="remarks"></a>解説

を使用し `ClassFactory` て、ユーザー定義のファクトリ実装を提供します。

次のプログラミングパターンは、 [Implements](implements-structure.md) 構造体を使用して、クラスファクトリに3つ以上のインターフェイスを指定する方法を示しています。

`struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                        | 説明
------------------------------------------- | -----------
[ClassFactory:: ClassFactory](#classfactory) |

### <a name="public-methods"></a>パブリック メソッド

名前                                            | 説明
----------------------------------------------- | ----------------------------------------------------------------------------------------------------------------
[ClassFactory:: AddRef](#addref)                 | 現在のオブジェクトの参照カウントをインクリメントし `ClassFactory` ます。
[ClassFactory:: LockServer](#lockserver)         | 現在のオブジェクトによって追跡される、基になるオブジェクトの数をインクリメントまたはデクリメントし `ClassFactory` ます。
[ClassFactory:: QueryInterface](#queryinterface) | パラメーターによって指定されたインターフェイスへのポインターを取得します。
[ClassFactory:: Release](#release)               | 現在のオブジェクトの参照カウントをデクリメントし `ClassFactory` ます。

## <a name="inheritance-hierarchy"></a>継承階層

`I0`

`ChainInterfaces`

`I0`

`RuntimeClassBase`

`ImplementsHelper`

`DontUseNewUseMake`

`RuntimeClassFlags`

`RuntimeClassBaseT`

`RuntimeClass`

`ClassFactory`

## <a name="requirements"></a>要件

**ヘッダー:** resource.h

**名前空間:** Microsoft::WRL

## <a name="classfactoryaddref"></a><a name="addref"></a> ClassFactory:: AddRef

現在のオブジェクトの参照カウントをインクリメントし `ClassFactory` ます。

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。

## <a name="classfactoryclassfactory"></a><a name="classfactory"></a> ClassFactory:: ClassFactory

```cpp
WRL_NOTHROW ClassFactory();
```

## <a name="classfactorylockserver"></a><a name="lockserver"></a> ClassFactory:: LockServer

現在のオブジェクトによって追跡される、基になるオブジェクトの数をインクリメントまたはデクリメントし `ClassFactory` ます。

```cpp
STDMETHOD(
   LockServer
)(BOOL fLock);
```

### <a name="parameters"></a>パラメーター

*fLock*<br/>
**`true`** 追跡するオブジェクトの数を増やす場合は。 **`false`** 追跡するオブジェクトの数を減らす場合は。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、E_FAIL ます。

### <a name="remarks"></a>解説

`ClassFactory`[モジュール](module-class.md)クラスの基になるインスタンスのオブジェクトを追跡します。

## <a name="classfactoryqueryinterface"></a><a name="queryinterface"></a> ClassFactory:: QueryInterface

パラメーターによって指定されたインターフェイスへのポインターを取得します。

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
インターフェイス ID。

*ppvObject*<br/>
この操作が完了したときに、パラメーター *riid* によって指定されたインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。

## <a name="classfactoryrelease"></a><a name="release"></a> ClassFactory:: Release

現在のオブジェクトの参照カウントをデクリメントし `ClassFactory` ます。

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。
