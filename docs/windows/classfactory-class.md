---
title: ClassFactory クラス |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory
- module/Microsoft::WRL::ClassFactory::AddRef
- module/Microsoft::WRL::ClassFactory::ClassFactory
- module/Microsoft::WRL::ClassFactory::LockServer
- module/Microsoft::WRL::ClassFactory::QueryInterface
- module/Microsoft::WRL::ClassFactory::Release
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::ClassFactory class
- Microsoft::WRL::ClassFactory::AddRef method
- Microsoft::WRL::ClassFactory::ClassFactory, constructor
- Microsoft::WRL::ClassFactory::LockServer method
- Microsoft::WRL::ClassFactory::QueryInterface method
- Microsoft::WRL::ClassFactory::Release method
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bfaf95a477917fc417cfe3c296822233eca77c09
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413069"
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
class ClassFactory : public Details::RuntimeClass<
   typename Details::InterfaceListHelper<IClassFactory,
   I0,
   I1,
   I2,
   Details::Nil>::TypeT,
   RuntimeClassFlags<ClassicCom | InhibitWeakReference>,
      false>;
```

### <a name="parameters"></a>パラメーター

*I0*<br/>
0 番目のインターフェイスです。

*I1*<br/>
最初のインターフェイス。

*I2*<br/>
2 番目のインターフェイス。

## <a name="remarks"></a>Remarks

利用`ClassFactory`工場出荷時のユーザー定義の実装を提供します。

次のプログラミングのパターンが使用する方法を示します、[実装](../windows/implements-structure.md)構造体をクラス ファクトリを複数の 3 つのインターフェイスを指定します。

`struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                        | 説明
------------------------------------------- | -----------
[Classfactory::classfactory](#classfactory) |

### <a name="public-methods"></a>パブリック メソッド

名前                                            | 説明
----------------------------------------------- | ----------------------------------------------------------------------------------------------------------------
[Classfactory::addref](#addref)                 | 現在の参照カウントをインクリメント`ClassFactory`オブジェクト。
[Classfactory::lockserver](#lockserver)         | ずつインクリメントまたはデクリメントし、現在追跡されるオブジェクトの基になる数`ClassFactory`オブジェクト。
[Classfactory::queryinterface](#queryinterface) | パラメーターで指定されたインターフェイスへのポインターを取得します。
[Classfactory::release](#release)               | 参照が現在のカウントをデクリメント`ClassFactory`オブジェクト。

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

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="addref"></a>Classfactory::addref

現在の参照カウントをインクリメント`ClassFactory`オブジェクト。

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。

## <a name="classfactory"></a>Classfactory::classfactory

```cpp
WRL_NOTHROW ClassFactory();
```

## <a name="lockserver"></a>Classfactory::lockserver

ずつインクリメントまたはデクリメントし、現在追跡されるオブジェクトの基になる数`ClassFactory`オブジェクト。

```cpp
STDMETHOD(
   LockServer
)(BOOL fLock);
```

### <a name="parameters"></a>パラメーター

*群れ*<br/>
`true` 追跡対象のオブジェクトの数をインクリメントします。 `false` 追跡対象のオブジェクトの数をデクリメントします。

### <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、E_FAIL します。

### <a name="remarks"></a>Remarks

`ClassFactory` 基になるインスタンス内のオブジェクトの追跡、[モジュール](../windows/module-class.md)クラス。

## <a name="queryinterface"></a>Classfactory::queryinterface

パラメーターで指定されたインターフェイスへのポインターを取得します。

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
インターフェイス ID。

*ppvObject*<br/>
ときにこの操作が完了すると、パラメーターで指定されたインターフェイスへのポインター *riid*します。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。

## <a name="release"></a>Classfactory::release

参照が現在のカウントをデクリメント`ClassFactory`オブジェクト。

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。
