---
title: HString クラス
ms.date: 07/15/2019
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString
- corewrappers/Microsoft::WRL::Wrappers::HString::Attach
- corewrappers/Microsoft::WRL::Wrappers::HString::CopyTo
- corewrappers/Microsoft::WRL::Wrappers::HString::Detach
- corewrappers/Microsoft::WRL::Wrappers::HString::Get
- corewrappers/Microsoft::WRL::Wrappers::HString::GetRawBuffer
- corewrappers/Microsoft::WRL::Wrappers::HString::GetAddressOf
- corewrappers/Microsoft::WRL::Wrappers::HString::HString
- corewrappers/Microsoft::WRL::Wrappers::HString::IsValid
- corewrappers/Microsoft::WRL::Wrappers::HString::MakeReference
- corewrappers/Microsoft::WRL::Wrappers::HString::operator=
- corewrappers/Microsoft::WRL::Wrappers::HString::operator==
- corewrappers/Microsoft::WRL::Wrappers::HString::operator!=
- corewrappers/Microsoft::WRL::Wrappers::HString::operator<
- corewrappers/Microsoft::WRL::Wrappers::HString::Release
- corewrappers/Microsoft::WRL::Wrappers::HString::Set
- corewrappers/Microsoft::WRL::Wrappers::HString::~HString
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HString class
- Microsoft::WRL::Wrappers::HString::Attach method
- Microsoft::WRL::Wrappers::HString::CopyTo method
- Microsoft::WRL::Wrappers::HString::Detach method
- Microsoft::WRL::Wrappers::HString::Get method
- Microsoft::WRL::Wrappers::HString::GetAddressOf method
- Microsoft::WRL::Wrappers::HString::HString, constructor
- Microsoft::WRL::Wrappers::HString::IsValid method
- Microsoft::WRL::Wrappers::HString::MakeReference method
- Microsoft::WRL::Wrappers::HString::operator= operator
- Microsoft::WRL::Wrappers::HString::operator== operator
- Microsoft::WRL::Wrappers::HString::operator!= operator
- Microsoft::WRL::Wrappers::HString::operator< operator
- Microsoft::WRL::Wrappers::HString::Release method
- Microsoft::WRL::Wrappers::HString::Set method
- Microsoft::WRL::Wrappers::HString::~HString, destructor
ms.assetid: 6709dd2e-8d72-4675-8ec7-1baa7d71854d
ms.openlocfilehash: 625d7b7d6fc001a6fb63144807b5f29d3620485b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371430"
---
# <a name="hstring-class"></a>HString クラス

RAII パターンを使用して[HSTRING](/windows/win32/WinRT/hstring)の有効期間を管理するためのヘルパー クラス。

## <a name="syntax"></a>構文

```cpp
class HString;
```

## <a name="remarks"></a>解説

Windows ランタイムは[、HSTRING](/windows/win32/WinRT/hstring)ハンドルを使用して文字列へのアクセスを提供します。 この`HString`クラスには、HSTRING ハンドルを使いやすくするための便利な関数と演算子が用意されています。 このクラスは RAII パターンを通じて、所有する HSTRING の有効期間を処理できます。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                | 説明
----------------------------------- | -----------------------------------------------------
[Hストリング::Hストリング](#hstring)        | `HString` クラスの新しいインスタンスを初期化します。
[Hストリング:~Hストリング](#tilde-hstring) | クラスの現在のインスタンスを破棄`HString`します。

### <a name="public-methods"></a>パブリック メソッド

名前                                     | 説明
---------------------------------------- | -------------------------------------------------------------------------------------------------------------
[文字列::アタッチ](#attach)               | 指定した`HString`オブジェクトを現在`HString`のオブジェクトに関連付けます。
[HString::CopyTo](#copyto)               | 現在`HString`のオブジェクトを HSTRING オブジェクトにコピーします。
[Hストリング::Dエタッハ](#detach)               | 指定した`HString`オブジェクトと基になる値の関連付けを解除します。
[Hストリング::取得](#get)                     | 基になる HSTRING ハンドルの値を取得します。
[文字列::ゲットアドレスの](#getaddressof)   | 基になる HSTRING ハンドルへのポインターを取得します。
[を文字列::バッファバッファ](#getrawbuffer)   | 基になる文字列データへのポインターを取得します。
[文字列::IsValid](#isvalid)             | 現在`HString`のオブジェクトが有効かどうかを示します。
[文字列::参照を作成します。](#makereference) | 指定した`HStringReference`文字列パラメーターからオブジェクトを作成します。
[Hストリング::リリース](#release)             | 基になる文字列値を削除し、現在`HString`のオブジェクトを空の値に初期化します。
[文字列::セット](#set)                     | 現在`HString`のオブジェクトの値を、指定されたワイド文字の文字列または`HString`パラメーターに設定します。

### <a name="public-operators"></a>パブリック演算子

名前                                         | 説明
-------------------------------------------- | ----------------------------------------------------------------------------
[文字列::演算子=](#operator-assign)       | 別`HString`のオブジェクトの値を現在`HString`のオブジェクトに移動します。
[H文字列::演算子==](#operator-equality)    | 2 つのパラメーターが等しいかどうかを示します。
[文字列::演算子!](#operator-inequality)  | 2 つのパラメーターが異なるかどうかを示します。
[文字列::演算子&lt;](#operator-less-than) | 最初のパラメーターが 2 番目のパラメーターより小さいかどうかを示します。

## <a name="inheritance-hierarchy"></a>継承階層

`HString`

## <a name="requirements"></a>必要条件

**ヘッダー:** コアラッパー.h

**名前空間:** マイクロソフト::WRL::ラッパー

## <a name="hstringhstring"></a><a name="tilde-hstring"></a>Hストリング:~Hストリング

クラスの現在のインスタンスを破棄`HString`します。

```cpp
~HString() throw()
```

## <a name="hstringattach"></a><a name="attach"></a>文字列::アタッチ

指定した`HString`オブジェクトを現在`HString`のオブジェクトに関連付けます。

```cpp
void Attach(
       HSTRING hstr
       ) throw()
```

### <a name="parameters"></a>パラメーター

*hstr*<br/>
既存の `HString` オブジェクトです。

## <a name="hstringcopyto"></a><a name="copyto"></a>文字列::コピート

現在`HString`のオブジェクトを HSTRING オブジェクトにコピーします。

```cpp
HRESULT CopyTo(
   _Out_ HSTRING *str
   ) const throw();
```

### <a name="parameters"></a>パラメーター

*Str*<br/>
コピーを受信する HSTRING です。

### <a name="remarks"></a>解説

このメソッドは、関数を呼び出[します](/windows/win32/api/winstring/nf-winstring-windowsduplicatestring)。

## <a name="hstringdetach"></a><a name="detach"></a>Hストリング::Dエタッハ

指定した`HString`オブジェクトと基になる値の関連付けを解除します。

```cpp
HSTRING Detach() throw()
```

### <a name="return-value"></a>戻り値

デタッチ`HString`操作が開始される前の基になる値。

## <a name="hstringget"></a><a name="get"></a>Hストリング::取得

基になる HSTRING ハンドルの値を取得します。

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>戻り値

基になる HSTRING ハンドルの値

## <a name="hstringgetaddressof"></a><a name="getaddressof"></a>文字列::ゲットアドレスの

基になる HSTRING ハンドルへのポインターを取得します。

```cpp
HSTRING* GetAddressOf() throw()
```

### <a name="return-value"></a>戻り値

基になる HSTRING ハンドルへのポインター。

### <a name="remarks"></a>解説

この操作の後、基になる HSTRING ハンドルの文字列値が破棄されます。

## <a name="hstringgetrawbuffer"></a><a name="getrawbuffer"></a>を文字列::バッファバッファ

基になる文字列データへのポインターを取得します。

```cpp
const wchar_t* GetRawBuffer(unsigned int* length) const;
```

### <a name="parameters"></a>パラメーター

*長さ*データの長さを受け取る**int**変数へのポインター。

### <a name="return-value"></a>戻り値

基になる文字列データへの**const**ポインター。

## <a name="hstringhstring"></a><a name="hstring"></a>Hストリング::Hストリング

`HString` クラスの新しいインスタンスを初期化します。

```cpp
HString() throw();
HString(HString&& other) throw();
```

### <a name="parameters"></a>パラメーター

*hstr*<br/>
HSTRING ハンドル。

*他*<br/>
既存の `HString` オブジェクトです。

### <a name="remarks"></a>解説

最初のコンストラクターは、空の`HString`新しいオブジェクトを初期化します。

2 番目のコンストラクターは、`HString`新しいオブジェクトを既存の*他*のパラメーターの値に初期化し、*その他*のパラメーターを破棄します。

## <a name="hstringisvalid"></a><a name="isvalid"></a>文字列::IsValid

現在`HString`のオブジェクトが空かどうかを示します。

```cpp
bool IsValid() const throw()
```

### <a name="parameters"></a>パラメーター

現在`HString`のオブジェクトが空でない場合は true、空でない場合は**true。** それ以外の場合**は false。**

## <a name="hstringmakereference"></a><a name="makereference"></a>文字列::参照を作成します。

指定した`HStringReference`文字列パラメーターからオブジェクトを作成します。

```cpp
template<unsigned int sizeDest>
    static HStringReference MakeReference(
              wchar_t const (&str)[ sizeDest]);

    template<unsigned int sizeDest>
    static HStringReference MakeReference(
              wchar_t const (&str)[sizeDest],
              unsigned int len);
```

### <a name="parameters"></a>パラメーター

*サイズ最も大きな*<br/>
コピー先`HStringReference`のバッファーのサイズを指定するテンプレート パラメーター。

*Str*<br/>
ワイド文字列への参照。

*Len*<br/>
この操作で使用する*str*パラメーター バッファーの最大長。 *len*パラメーターが指定されていない場合は *、str*パラメーター全体が使用されます。

### <a name="return-value"></a>戻り値

指定`HStringReference`された*str*パラメーターと同じ値を持つオブジェクト。

## <a name="hstringoperator-operator"></a><a name="operator-assign"></a>H文字列::演算子= 演算子

別`HString`のオブジェクトの値を現在`HString`のオブジェクトに移動します。

```cpp
HString& operator=(HString&& other) throw()
```

### <a name="parameters"></a>パラメーター

*他*<br/>
既存の `HString` オブジェクトです。

### <a name="remarks"></a>解説

既存の*他*のオブジェクトの値が現在`HString`のオブジェクトにコピーされ、*その後、他*のオブジェクトが破棄されます。

## <a name="hstringoperator-operator"></a><a name="operator-equality"></a>H文字列::演算子==演算子

2 つのパラメーターが等しいかどうかを示します。

```cpp
inline bool operator==(
               const HString& lhs,
               const HString& rhs) throw()

inline bool operator==(
                const HString& lhs,
                const HStringReference& rhs) throw()

inline bool operator==(
                const HStringReference& lhs,
                const HString& rhs) throw()

inline bool operator==(
                 const HSTRING& lhs,
                 const HString& rhs) throw()

inline bool operator==(
                 const HString& lhs,
                 const HSTRING& rhs) throw()
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する最初のパラメーター。 *lhs*は、 `HString` `HStringReference`または オブジェクト、または HSTRING ハンドルです。

*rhs*<br/>
比較する 2 番目のパラメーター。*rhs*は、 `HString` `HStringReference`または オブジェクト、または HSTRING ハンドルです。

### <a name="return-value"></a>戻り値

*lhs*と*rhs*のパラメーターが等しい場合は**true。** それ以外の場合**は false。**

## <a name="hstringoperator-operator"></a><a name="operator-inequality"></a>H文字列::演算子!= 演算子

2 つのパラメーターが異なるかどうかを示します。

```cpp
inline bool operator!=( const HString& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HStringReference& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HString& lhs,
                        const HStringReference& rhs) throw()

inline bool operator!=( const HSTRING& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HString& lhs,
                        const HSTRING& rhs) throw()
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する最初のパラメーター。 *lhs*は、 `HString` `HStringReference`または オブジェクト、または HSTRING ハンドルです。

*rhs*<br/>
比較する 2 番目のパラメーター。*rhs*は、 `HString` `HStringReference`または オブジェクト、または HSTRING ハンドルです。

### <a name="return-value"></a>戻り値

*lhs*と*rhs*のパラメーターが等しくない場合は**true。** それ以外の場合**は false。**

## <a name="hstringoperatorlt-operator"></a><a name="operator-less-than"></a>H文字列::演算子&lt;演算子

最初のパラメーターが 2 番目のパラメーターより小さいかどうかを示します。

```cpp
inline bool operator<(
    const HString& lhs,
    const HString& rhs) throw()
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する最初のパラメーター。 *lhs*は、 への参照`HString`にすることができます。

*rhs*<br/>
比較する 2 番目のパラメーター。 *rhs*は への参照にすることができます`HString`。

### <a name="return-value"></a>戻り値

*lhs*パラメーターが*rhs*パラメーターより小さい場合は**true。** それ以外の場合**は false。**

## <a name="hstringrelease"></a><a name="release"></a>Hストリング::リリース

基になる文字列値を削除し、現在`HString`のオブジェクトを空の値に初期化します。

```cpp
void Release() throw()
```

## <a name="hstringset"></a><a name="set"></a>文字列::セット

現在`HString`のオブジェクトの値を、指定されたワイド文字の文字列または`HString`パラメーターに設定します。

```cpp
HRESULT Set(
          const wchar_t* str) throw();
HRESULT Set(
          const wchar_t* str,
          unsigned int len
           ) throw();
HRESULT Set(
          const HSTRING& hstr
           ) throw();
```

### <a name="parameters"></a>パラメーター

*Str*<br/>
ワイド文字列。

*Len*<br/>
現在`HString`のオブジェクトに割り当てられている*str*パラメーターの最大長。

*hstr*<br/>
既存の `HString` オブジェクトです。
