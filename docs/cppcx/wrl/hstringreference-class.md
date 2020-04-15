---
title: HStringReference クラス
ms.date: 07/15/2019
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::CopyTo
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::Get
- corewrappers/Microsoft::WRL::Wrappers::GetRawBuffer
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator==
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator!=
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator<
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HStringReference class
- Microsoft::WRL::Wrappers::HStringReference::CopyTo method
- Microsoft::WRL::Wrappers::HStringReference::Get method
- Microsoft::WRL::Wrappers::HStringReference::HStringReference, constructor
- Microsoft::WRL::Wrappers::HStringReference::operator= operator
- Microsoft::WRL::Wrappers::HStringReference::operator== operator
- Microsoft::WRL::Wrappers::HStringReference::operator!= operator
- Microsoft::WRL::Wrappers::HStringReference::operator< operator
ms.assetid: 9bf823b1-17eb-4ac4-8c5d-27d27c7a4150
ms.openlocfilehash: fd064f97081fad1a9df9de0865bb7c46ad5b4484
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371421"
---
# <a name="hstringreference-class"></a>HStringReference クラス

既存の文字列から作成された HSTRING を表します。

## <a name="syntax"></a>構文

```cpp
class HStringReference;
```

## <a name="remarks"></a>解説

新しい HSTRING でのバッキング バッファーの有効期間は、Windows ランタイムによって管理されません。 呼び出し元はソース文字列をスタック フレームに割り当てることで、ヒープ割り当てを回避し、メモリ リークのリスクを排除します。 また、呼び出し元はアタッチ済みの HSTRING の有効期間中にソース文字列が変更されないことを確認する必要があります。 詳細については、「[関数を作成する」を参照してください](/windows/win32/api/winstring/nf-winstring-windowscreatestringreference)。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                    | 説明
------------------------------------------------------- | -----------------------------------------------------------
[文字列参照:Hストリングリファレンス](#hstringreference) | `HStringReference` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

メンバー                              | 説明
----------------------------------- | ------------------------------------------------------------------
[HStringReference::CopyTo](#copyto) | 現在`HStringReference`のオブジェクトを HSTRING オブジェクトにコピーします。
[文字列参照:取得](#get)       | 基になる HSTRING ハンドルの値を取得します。
[を参照します。](#getrawbuffer) | 基になる文字列データへのポインターを取得します。

### <a name="public-operators"></a>パブリック演算子

名前                                                  | 説明
----------------------------------------------------- | ----------------------------------------------------------------------------------------------
[参照::演算子=](#operator-assign)       | 別`HStringReference`のオブジェクトの値を現在`HStringReference`のオブジェクトに移動します。
[参照:演算子==](#operator-equality)    | 2 つのパラメーターが等しいかどうかを示します。
[文字列参照::演算子!=](#operator-inequality)  | 2 つのパラメーターが異なるかどうかを示します。
[文字列参照::演算子&lt;](#operator-less-than) | 最初のパラメーターが 2 番目のパラメーターより小さいかどうかを示します。

## <a name="inheritance-hierarchy"></a>継承階層

`HStringReference`

## <a name="requirements"></a>必要条件

**ヘッダー:** コアラッパー.h

**名前空間:** マイクロソフト::WRL::ラッパー

## <a name="hstringreferencecopyto"></a><a name="copyto"></a>文字列参照:コピー先

現在`HStringReference`のオブジェクトを HSTRING オブジェクトにコピーします。

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

## <a name="hstringreferenceget"></a><a name="get"></a>文字列参照:取得

基になる HSTRING ハンドルの値を取得します。

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>戻り値

基になる HSTRING ハンドルの値。

## <a name="hstringreferencegetrawbuffer"></a><a name="getrawbuffer"></a>を参照します。

基になる文字列データへのポインターを取得します。

```cpp
const wchar_t* GetRawBuffer(unsigned int* length) const;
```

### <a name="parameters"></a>パラメーター

*長さ*データの長さを受け取る**int**変数へのポインター。

### <a name="return-value"></a>戻り値

基になる文字列データへの**const**ポインター。

## <a name="hstringreferencehstringreference"></a><a name="hstringreference"></a>文字列参照:Hストリングリファレンス

`HStringReference` クラスの新しいインスタンスを初期化します。

```cpp
template<unsigned int sizeDest>
HStringReference(wchar_t const (&str)[ sizeDest]) throw();

template<unsigned int sizeDest>
HStringReference(wchar_t const (&str)[ sizeDest],
                 unsigned int len) throw();

HStringReference(HStringReference&& other) throw();
```

### <a name="parameters"></a>パラメーター

*サイズ最も大きな*<br/>
コピー先`HStringReference`のバッファーのサイズを指定するテンプレート パラメーター。

*Str*<br/>
ワイド文字列への参照。

*Len*<br/>
この操作で使用する*str*パラメーター バッファーの最大長。 *len*パラメーターが指定されていない場合は *、str*パラメーター全体が使用されます。 *len*が*sizeDest*より大きい場合 *、len*は*sizeDest*-1 に設定されます。

*他*<br/>
別`HStringReference`のオブジェクト。

### <a name="remarks"></a>解説

最初のコンストラクターは、パラメーター `HStringReference` *str*と同じサイズの新しいオブジェクトを初期化します。

2 番目のコンストラクターは、`HStringReference`パラメーター *len*によって指定されたサイズの新しいオブジェクトを初期化します。

3 番目のコンストラクターは、`HStringReference`新しいオブジェクトを*他*のパラメーターの値に初期化し、*その後、他*のパラメーターを破棄します。

## <a name="hstringreferenceoperator"></a><a name="operator-assign"></a>参照::演算子=

別`HStringReference`のオブジェクトの値を現在`HStringReference`のオブジェクトに移動します。

```cpp
HStringReference& operator=(HStringReference&& other) throw()
```

### <a name="parameters"></a>パラメーター

*他*<br/>
既存の `HStringReference` オブジェクトです。

### <a name="remarks"></a>解説

既存の*他*のオブジェクトの値が現在`HStringReference`のオブジェクトにコピーされ、*その後、他*のオブジェクトが破棄されます。

## <a name="hstringreferenceoperator"></a><a name="operator-equality"></a>参照:演算子==

2 つのパラメーターが等しいかどうかを示します。

```cpp
inline bool operator==(
               const HStringReference& lhs,
               const HStringReference& rhs) throw()

inline bool operator==(
               const HSTRING& lhs,
               const HStringReference& rhs) throw()

inline bool operator==(
               const HStringReference& lhs,
               const HSTRING& rhs) throw()
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する最初のパラメーター。 *lhs*は`HStringReference`、オブジェクトまたは HSTRING ハンドルにすることができます。

*rhs*<br/>
比較する 2 番目のパラメーター。  *rhs*は`HStringReference`オブジェクトまたは HSTRING ハンドルにすることができます。

### <a name="return-value"></a>戻り値

*lhs*と*rhs*のパラメーターが等しい場合は**true。** それ以外の場合**は false。**

## <a name="hstringreferenceoperator"></a><a name="operator-inequality"></a>文字列参照::演算子!=

2 つのパラメーターが異なるかどうかを示します。

```cpp
inline bool operator!=(
               const HStringReference& lhs,
               const HStringReference& rhs) throw()

inline bool operator!=(
               const HSTRING& lhs,
               const HStringReference& rhs) throw()

inline bool operator!=(
               const HStringReference& lhs,
               const HSTRING& rhs) throw()
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する最初のパラメーター。 *lhs*は`HStringReference`、オブジェクトまたは HSTRING ハンドルにすることができます。

*rhs*<br/>
比較する 2 番目のパラメーター。  *rhs*は`HStringReference`オブジェクトまたは HSTRING ハンドルにすることができます。

### <a name="return-value"></a>戻り値

*lhs*と*rhs*のパラメーターが等しくない場合は**true。** それ以外の場合**は false。**

## <a name="hstringreferenceoperatorlt"></a><a name="operator-less-than"></a>文字列参照::演算子&lt;

最初のパラメーターが 2 番目のパラメーターより小さいかどうかを示します。

```cpp
inline bool operator<(
    const HStringReference& lhs,
    const HStringReference& rhs) throw()
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する最初のパラメーター。 *lhs*は、 への参照`HStringReference`にすることができます。

*rhs*<br/>
比較する 2 番目のパラメーター。  *rhs*は への参照にすることができます`HStringReference`。

### <a name="return-value"></a>戻り値

*lhs*パラメーターが*rhs*パラメーターより小さい場合は**true。** それ以外の場合**は false。**
