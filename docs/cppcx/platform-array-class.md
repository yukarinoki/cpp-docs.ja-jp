---
title: Platform::Array クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Array
- VCCORLIB/Platform::Array::Value
helpviewer_keywords:
- Platform::Array Class
ms.assetid: 7815ab40-88c5-42b0-83b8-081cef0cda31
ms.openlocfilehash: 4903c18f981c87c418a6ab08595816ce22a7413c
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742945"
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

Platform:: Array は、 [platform:: WriteOnlyArray クラス](../cppcx/platform-writeonlyarray-class.md) からすべてのメソッドを継承し、 `Value` [Platform:: iboxarray インターフェイス](../cppcx/platform-iboxarray-interface.md)のプロパティを実装します。

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Array コンストラクター](#ctor)|クラステンプレートパラメーター *T*によって指定された型の、変更可能な1次元配列を初期化します。|

### <a name="methods"></a>メソッド

[Platform:: WriteOnlyArray クラス](../cppcx/platform-writeonlyarray-class.md)を参照してください。

### <a name="properties"></a>Properties

| 名前 | 説明 |
|--|--|
| [Array:: Value](#value) | 現在の配列へのハンドルを取得します。 |

### <a name="remarks"></a>注釈

この Array クラスはシール クラスであり、継承できません。

Windows ランタイム型システムは、ジャグ配列の概念をサポートしていないため、を `IVector<Platform::Array<T>>` 戻り値またはメソッドパラメーターとして渡すことはできません。 ABI を通じてジャグ配列またはシーケンスのシーケンスを渡すには、 `IVector<IVector<T>^>`を使用します。

Platform:: Array を使用するタイミングと方法の詳細については、「 [array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)」を参照してください。

このクラスは、コンパイラによって自動的に含まれる vccorlib.h ヘッダーで定義されます。 これは、IntelliSense では表示できますが、オブジェクトブラウザーでは表示されません。これは、platform. winmd で定義されているパブリック型ではないためです。

### <a name="requirements"></a>必要条件

コンパイラ オプション: **/ZW**

## <a name="array-constructors"></a><a name="ctor"></a> 配列コンストラクター

クラステンプレートパラメーター *T*によって指定された型の、変更可能な1次元配列を初期化します。

### <a name="syntax"></a>構文

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

### <a name="remarks"></a>注釈

Platform:: Array のインスタンスを作成する方法の詳細については、「 [array および WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)」を参照してください。

## <a name="arrayget-method"></a><a name="get"></a> Array:: get メソッド

指定されたインデックス位置にある配列要素への参照を取得します。

### <a name="syntax"></a>構文

```cpp
T& get(unsigned int index)  const;
```

#### <a name="parameters"></a>パラメーター

*インデックス*<br/>
配列の要素を識別する 0 から始まるインデックス。 最小インデックスは0、最大インデックスは `size` [配列コンストラクター](#ctor)のパラメーターによって指定された値です。

### <a name="return-value"></a>戻り値

`index` パラメーターで指定された配列要素。

## <a name="arrayvalue-property"></a><a name="value"></a> Array:: Value プロパティ

現在の配列へのハンドルを取得します。

### <a name="syntax"></a>構文

```cpp
property Array^ Value;
```

### <a name="return-value"></a>戻り値

現在の配列へのハンドル。

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)<br/>
[Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)
