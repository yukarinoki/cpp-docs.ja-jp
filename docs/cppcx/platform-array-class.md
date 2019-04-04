---
title: Platform::Array クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Array Constructors
- VCCORLIB/Namespace not found::Platform::Array::Value
helpviewer_keywords:
- Platform::Array Class
ms.assetid: 7815ab40-88c5-42b0-83b8-081cef0cda31
ms.openlocfilehash: 597f8e32e2da95370169cdbfe2ccd209296322cc
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751662"
---
# <a name="platformarray-class"></a>Platform::Array クラス

アプリケーション バイナリ インターフェイス (ABI) を越えて受け渡しでき、変更もできる 1 次元配列を表します。

## <a name="syntax"></a>構文

```cpp
template <typename T>
private ref class Array<TArg, 1> :
    public WriteOnlyArray<TArg, 1>,
    public IBoxArray<TArg>
```

### <a name="members"></a>メンバー

Platform::array からすべてのメソッドを継承する[platform::writeonlyarray クラス](../cppcx/platform-writeonlyarray-class.md)を実装して、`Value`のプロパティ、 [platform::iboxarray インターフェイス](../cppcx/platform-iboxarray-interface.md)します。

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Array コンストラクター](#ctor)|クラス テンプレート パラメーターで指定された型の変更可能な 1 次元配列を初期化します*T*します。|

### <a name="methods"></a>メソッド

参照してください[platform::writeonlyarray クラス](../cppcx/platform-writeonlyarray-class.md)します。

### <a name="properties"></a>プロパティ

|||
|-|-|
|[Array::value](#value)|現在の配列へのハンドルを取得します。|

### <a name="remarks"></a>Remarks

この Array クラスはシール クラスであり、継承できません。

Windows ランタイムの型システムは、ジャグ配列の概念をサポートしていませんし、そのため、IVector を渡すことはできません < platform::array\<T >> を戻り値またはメソッド パラメーターとして。 ABI を通じてジャグ配列またはシーケンスのシーケンスを渡すには、 `IVector<IVector<T>^>`を使用します。

Platform::array を使用するタイミングと方法の詳細については、[Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)を参照してください。

Windows ランタイムの型システムは、ジャグ配列の概念をサポートしていませんし、そのため、IVector を渡すことはできません < platform::array\<T >> を戻り値またはメソッド パラメーターとして。 ABI を通じてジャグ配列またはシーケンスのシーケンスを渡すには、 `IVector<IVector<T>^>`を使用します。

このクラスは、コンパイラによって自動的に含まれる vccorlib.h ヘッダーで定義されます。 これは、方法は、platform.winmd で定義されているパブリック型ではないため、IntelliSense が含まれないオブジェクト ブラウザーに表示されます。

### <a name="requirements"></a>必要条件

コンパイラ オプション: **/ZW**

## <a name="ctor"></a>  Array コンス トラクター

クラス テンプレート パラメーターで指定された型の変更可能な 1 次元配列を初期化します*T*します。

## <a name="syntax"></a>構文

```cpp
Array(unsigned int size);
Array(T* data, unsigned int size);
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
クラス テンプレート パラメーター。

*size*<br/>
配列の要素数。

*data*<br/>
この Array オブジェクトを初期化するために使用する型 `T` のデータ配列へのポインター。

### <a name="remarks"></a>Remarks

Platform::array のインスタンスを作成する方法の詳細については、[Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)を参照してください。

## <a name="get"></a>  Array::get メソッド

指定されたインデックス位置にある配列要素への参照を取得します。

## <a name="syntax"></a>構文

```cpp
T& get(unsigned int index)  const;
```

#### <a name="parameters"></a>パラメーター

*index*<br/>
配列の要素を識別する 0 から始まるインデックス。 最小のインデックスは 0 と最大のインデックスがで指定された値、`size`パラメーター、[配列コンス トラクター](#ctor)します。

### <a name="return-value"></a>戻り値


  `index` パラメーターで指定された配列要素。

## <a name="value"></a>  Array::value プロパティ

現在の配列へのハンドルを取得します。

## <a name="syntax"></a>構文

```cpp
property Array^ Value;
```

### <a name="return-value"></a>戻り値

現在の配列へのハンドル。

## <a name="see-also"></a>関連項目

[Platform 名前空間](../cppcx/platform-namespace-c-cx.md)<br/>
[Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)
