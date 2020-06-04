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
ms.openlocfilehash: d625d80df67a3c8207467ad629afd4c2bf88db18
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318656"
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

プラットフォーム::配列は、プラットフォームからすべてのメソッドを継承します[:WriteOnlyArrayクラス](../cppcx/platform-writeonlyarray-class.md)とのプロパティ`Value`を実装します[Platform::IBoxArray Interface](../cppcx/platform-iboxarray-interface.md)。

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Array コンストラクター](#ctor)|クラス テンプレート パラメーター *T*で指定された型の 1 次元の変更可能な配列を初期化します。|

### <a name="methods"></a>メソッド

[「プラットフォーム::WriteOnlyArray クラス](../cppcx/platform-writeonlyarray-class.md)」を参照してください。

### <a name="properties"></a>プロパティ

|||
|-|-|
|[配列::値](#value)|現在の配列へのハンドルを取得します。|

### <a name="remarks"></a>解説

この Array クラスはシール クラスであり、継承できません。

Windows ランタイム型システムは、ジャグ配列の概念をサポートしていないため、IVector<プラットフォーム::配列\<T>> を戻り値またはメソッド パラメーターとして渡すことはできません。 ABI を通じてジャグ配列またはシーケンスのシーケンスを渡すには、 `IVector<IVector<T>^>`を使用します。

プラットフォームを使用するタイミングと方法の詳細については、「[配列と WriteOnlyArray」](../cppcx/array-and-writeonlyarray-c-cx.md)を参照してください。

このクラスは、コンパイラによって自動的に含まれる vccorlib.h ヘッダーで定義されます。 これは、platform.winmd で定義されたパブリック型ではないため、IntelliSense では表示されますが、オブジェクト ブラウザーでは表示されません。

### <a name="requirements"></a>必要条件

コンパイラ オプション: **/ZW**

## <a name="array-constructors"></a><a name="ctor"></a>配列コンストラクタ

クラス テンプレート パラメーター *T*で指定された型の 1 次元の変更可能な配列を初期化します。

## <a name="syntax"></a>構文

```cpp
Array(unsigned int size);
Array(T* data, unsigned int size);
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
クラス テンプレート パラメーター。

*サイズ*<br/>
配列の要素数。

*データ*<br/>
この Array オブジェクトを初期化するために使用する型 `T` のデータ配列へのポインター。

### <a name="remarks"></a>解説

プラットフォームのインスタンスを作成する方法の詳細については、「[配列と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)」を参照してください。

## <a name="arrayget-method"></a><a name="get"></a>配列::メソッドを取得します。

指定されたインデックス位置にある配列要素への参照を取得します。

## <a name="syntax"></a>構文

```cpp
T& get(unsigned int index)  const;
```

#### <a name="parameters"></a>パラメーター

*index*<br/>
配列の要素を識別する 0 から始まるインデックス。 最小インデックスは 0 で、最大インデックスは Array コンストラクタ`size`のパラメータで指定された値[です](#ctor)。

### <a name="return-value"></a>戻り値

`index` パラメーターで指定された配列要素。

## <a name="arrayvalue-property"></a><a name="value"></a>配列::値プロパティ

現在の配列へのハンドルを取得します。

## <a name="syntax"></a>構文

```cpp
property Array^ Value;
```

### <a name="return-value"></a>戻り値

現在の配列へのハンドル。

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)<br/>
[Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)
