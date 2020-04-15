---
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
ms.openlocfilehash: 3b738cc8f439e6653162ab99b0a26e87aa8fee36
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372665"
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
0 番目のインターフェイス。

*I1*<br/>
最初のインターフェイス。

*I2*<br/>
2 番目のインターフェイス。

## <a name="remarks"></a>解説

ユーザー`ClassFactory`定義のファクトリ実装を提供するために利用します。

次のプログラミング パターンは[、Implements](implements-structure.md)構造体を使用してクラス ファクトリで 3 つ以上のインターフェイスを指定する方法を示しています。

`struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                        | 説明
------------------------------------------- | -----------
[クラスファクトリー::クラスファクトリー](#classfactory) |

### <a name="public-methods"></a>パブリック メソッド

名前                                            | 説明
----------------------------------------------- | ----------------------------------------------------------------------------------------------------------------
[クラスファクトリー::AddRef](#addref)                 | 現在`ClassFactory`のオブジェクトの参照カウントをインクリメントします。
[クラスファクトリー::ロックサーバー](#lockserver)         | 現在`ClassFactory`のオブジェクトによって追跡される基になるオブジェクトの数をインクリメントまたはデクリメントします。
[クラスファクトリー::クエリインターフェイス](#queryinterface) | パラメーターで指定されたインターフェイスへのポインターを取得します。
[クラスファクトリー::リリース](#release)               | 現在`ClassFactory`のオブジェクトの参照カウントを減算します。

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

## <a name="requirements"></a>必要条件

**ヘッダー:** モジュール.h

**名前空間:** Microsoft::WRL

## <a name="classfactoryaddref"></a><a name="addref"></a>クラスファクトリー::AddRef

現在`ClassFactory`のオブジェクトの参照カウントをインクリメントします。

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。

## <a name="classfactoryclassfactory"></a><a name="classfactory"></a>クラスファクトリー::クラスファクトリー

```cpp
WRL_NOTHROW ClassFactory();
```

## <a name="classfactorylockserver"></a><a name="lockserver"></a>クラスファクトリー::ロックサーバー

現在`ClassFactory`のオブジェクトによって追跡される基になるオブジェクトの数をインクリメントまたはデクリメントします。

```cpp
STDMETHOD(
   LockServer
)(BOOL fLock);
```

### <a name="parameters"></a>パラメーター

*群れ*<br/>
追跡対象オブジェクトの数を増やす場合は**true。** 追跡対象オブジェクトの数を減らすには**false。**

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、E_FAIL。

### <a name="remarks"></a>解説

`ClassFactory`[は、Module](module-class.md)クラスの基になるインスタンス内のオブジェクトを追跡します。

## <a name="classfactoryqueryinterface"></a><a name="queryinterface"></a>クラスファクトリー::クエリインターフェイス

パラメーターで指定されたインターフェイスへのポインターを取得します。

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
インターフェイス ID。

*オブジェクト*<br/>
この操作が完了すると、パラメータ*riid*で指定されたインターフェイスへのポインタ。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。

## <a name="classfactoryrelease"></a><a name="release"></a>クラスファクトリー::リリース

現在`ClassFactory`のオブジェクトの参照カウントを減算します。

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。
