---
title: Platform::WriteOnlyArray クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::WriteOnlyArray::begin
- VCCORLIB/Platform::WriteOnlyArray::Data
- VCCORLIB/Platform::WriteOnlyArray::end
- VCCORLIB/Platform::WriteOnlyArray::FastPass
- VCCORLIB/Platform::WriteOnlyArray::Length
- VCCORLIB/Platform::WriteOnlyArray::set
helpviewer_keywords:
- Platform::WriteOnlyArray Class
ms.assetid: 92d7dd56-ec58-4b8c-88ba-9c903668b687
ms.openlocfilehash: d06ed19b7c041f9ae73f862ba521449a206aa321
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374641"
---
# <a name="platformwriteonlyarray-class"></a>Platform::WriteOnlyArray クラス

メソッドで設定する配列を呼び出し元から渡すときに入力パラメーターとして使用される 1 次元配列を表します。

この ref クラスは vccorlib.h でプライベートとして宣言されています。したがって、メタデータには出力されず、C++ からのみ使用できます。 このクラスは、呼び出し元が割り当てた配列を受け取る入力パラメーターとして使用することのみを目的としています。 ユーザー コードから構築することはできません。 このクラスでは、C++ メソッドでその配列に直接書き込むことができます。このパターンは、 *FillArray* パターンと呼ばれます。 詳細については、「[配列と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)」を参照してください。

## <a name="syntax"></a>構文

```cpp
private ref class WriteOnlyArray<T, 1>
```

### <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

これらのメソッドのアクセシビリティは内部です。つまり、これらのメソッドには C++ アプリまたはコンポーネント内でのみアクセスできます。

|名前|説明|
|----------|-----------------|
|[書き込み専用配列::開始](#begin)|配列内の最初の要素を指す反復子。|
|[書き込み専用アレイ::Dアタ](#data)|データ バッファーへのポインター。|
|[書き込み専用配列::終了](#end)|配列内の最後の要素の 1 つ後ろを指す反復子。|
|[ライトオンリストアレイ::ファストパス](#fastpass)|配列が FastPass 機構を使用できるかどうかを示します。この機構は、システムで透過的に実行される最適化です。 コード内でこのプロパティを使用しないでください。|
|[書き込み専用配列::長さ](#length)|配列内の要素の数を返します。|
|[書き込み専用配列::セット](#set)|指定した要素を指定した値に設定します。|

## <a name="inheritance-hierarchy"></a>継承階層

`WriteOnlyArray`

### <a name="requirements"></a>必要条件

コンパイラ オプション: **/ZW**

**メタデータ:** Platform.winmd

**名前空間:** Platform

## <a name="writeonlyarraybegin-method"></a><a name="begin"></a>メソッドを開始します。

配列内の最初の要素へのポインターを返します。

### <a name="syntax"></a>構文

```cpp
T* begin() const;
```

### <a name="return-value"></a>戻り値

配列内の最初の要素へのポインター。

### <a name="remarks"></a>解説

この反復子は、配列の要素を操作するために `std::sort` などの STL アルゴリズムと共に使用できます。

## <a name="writeonlyarraydata-property"></a><a name="data"></a>書き込み専用配列::Data プロパティ

データ バッファーへのポインター。

### <a name="syntax"></a>構文

```cpp
property T* Data{
   T* get() const;
}
```

### <a name="return-value"></a>戻り値

生配列バイトへのポインター。

## <a name="writeonlyarrayend-method"></a><a name="end"></a>メソッドの終了

配列内の最後の要素の 1 つ後ろを指すポインターを返します。

### <a name="syntax"></a>構文

```cpp
T* end() const;
```

### <a name="return-value"></a>戻り値

配列内の最後の要素の 1 つ後ろを指すポインター反復子。

### <a name="remarks"></a>解説

この反復子は、配列要素に対して `std::sort` などの操作を実行するために STL アルゴリズムと共に使用できます。

## <a name="writeonlyarrayfastpass-property"></a><a name="fastpass"></a>ライトオンリストアレイ::ファストパスプロパティ

内部の FastPass 最適化を実行できるかどうかを示します。 ユーザー コードでの使用を目的としたものではありません。

### <a name="syntax"></a>構文

```cpp
property bool FastPass{
   bool get() const;
}
```

### <a name="return-value"></a>戻り値

配列が FastPass かどうかを示すブール値。

## <a name="writeonlyarrayget-method"></a><a name="get"></a>メソッドを取得します。

指定したインデックス位置にある要素を返します。

### <a name="syntax"></a>構文

```cpp
T& get(unsigned int indexArg) const;
```

### <a name="parameters"></a>パラメーター

*インデックス引数*<br/>
使用するインデックス。

### <a name="return-value"></a>戻り値

## <a name="writeonlyarraylength-property"></a><a name="length"></a>プロパティの長さ

呼び出し元が割り当てた配列内の要素の数を返します。

### <a name="syntax"></a>構文

```cpp
property unsigned int Length{
   unsigned int get() const;
}
```

### <a name="return-value"></a>戻り値

配列の要素数。

## <a name="writeonlyarrayset-function"></a><a name="set"></a>関数を設定します。

配列内の指定されたインデックス位置に指定された値を設定します。

### <a name="syntax"></a>構文

```cpp
T& set(
   unsigned int indexArg,
   T valueArg);
```

### <a name="parameters"></a>パラメーター

*インデックス引数*<br/>
設定する要素のインデックス。

*値Arg*<br/>
`indexArg` に設定する値。

### <a name="return-value"></a>戻り値

設定された要素への参照。

### <a name="remarks"></a>解説

HRESULT 値を解釈する方法の詳細については[、「COM エラー コードの構造](/windows/win32/com/structure-of-com-error-codes)」を参照してください。

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](platform-namespace-c-cx.md)<br/>
[C++ で Windows ランタイム コンポーネントを作成する](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
