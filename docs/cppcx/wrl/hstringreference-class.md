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
ms.openlocfilehash: 871696f4a970b1ef9d1f5d36d2e17184b93c9e8b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212983"
---
# <a name="hstringreference-class"></a>HStringReference クラス

既存の文字列から作成された HSTRING を表します。

## <a name="syntax"></a>構文

```cpp
class HStringReference;
```

## <a name="remarks"></a>解説

新しい HSTRING のバッキングバッファーの有効期間は、Windows ランタイムによって管理されていません。 呼び出し元はソース文字列をスタック フレームに割り当てることで、ヒープ割り当てを回避し、メモリ リークのリスクを排除します。 また、呼び出し元はアタッチ済みの HSTRING の有効期間中にソース文字列が変更されないことを確認する必要があります。 詳細については、「 [WindowsCreateStringReference 関数](/windows/win32/api/winstring/nf-winstring-windowscreatestringreference)」を参照してください。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                    | [説明]
------------------------------------------------------- | -----------------------------------------------------------
[HStringReference:: HStringReference](#hstringreference) | `HStringReference` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

メンバー                              | 説明
----------------------------------- | ------------------------------------------------------------------
[HStringReference::CopyTo](#copyto) | 現在の `HStringReference` オブジェクトを HSTRING オブジェクトにコピーします。
[HStringReference:: Get](#get)       | 基になる HSTRING ハンドルの値を取得します。
[HStringReference:: GetRawBuffer](#getrawbuffer) | 基になる文字列データへのポインターを取得します。

### <a name="public-operators"></a>パブリック演算子

名前                                                  | [説明]
----------------------------------------------------- | ----------------------------------------------------------------------------------------------
[HStringReference:: operator =](#operator-assign)       | 別のオブジェクトの値 `HStringReference` を現在のオブジェクトに移動 `HStringReference` します。
[HStringReference:: operator = =](#operator-equality)    | 2 つのパラメーターが等しいかどうかを示します。
[HStringReference:: operator! =](#operator-inequality)  | 2 つのパラメーターが異なるかどうかを示します。
[HStringReference:: operator&lt;](#operator-less-than) | 最初のパラメーターが2番目のパラメーターより小さいかどうかを示します。

## <a name="inheritance-hierarchy"></a>継承階層

`HStringReference`

## <a name="requirements"></a>必要条件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper

## <a name="hstringreferencecopyto"></a><a name="copyto"></a>HStringReference:: CopyTo

現在の `HStringReference` オブジェクトを HSTRING オブジェクトにコピーします。

```cpp
HRESULT CopyTo(
   _Out_ HSTRING *str
   ) const throw();
```

### <a name="parameters"></a>パラメーター

*引数*<br/>
コピーを受信する HSTRING です。

### <a name="remarks"></a>解説

このメソッドは、 [WindowsDuplicateString](/windows/win32/api/winstring/nf-winstring-windowsduplicatestring)関数を呼び出します。

## <a name="hstringreferenceget"></a><a name="get"></a>HStringReference:: Get

基になる HSTRING ハンドルの値を取得します。

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>戻り値

基になる HSTRING ハンドルの値。

## <a name="hstringreferencegetrawbuffer"></a><a name="getrawbuffer"></a>HStringReference:: GetRawBuffer

基になる文字列データへのポインターを取得します。

```cpp
const wchar_t* GetRawBuffer(unsigned int* length) const;
```

### <a name="parameters"></a>パラメーター

*長さ***`int`** データの長さを受け取る変数へのポインター。

### <a name="return-value"></a>戻り値

**`const`** 基になる文字列データへのポインター。

## <a name="hstringreferencehstringreference"></a><a name="hstringreference"></a>HStringReference:: HStringReference

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

*sizeDest*<br/>
コピー先のバッファーのサイズを指定するテンプレートパラメーター `HStringReference` 。

*引数*<br/>
ワイド文字列への参照。

*len*<br/>
この操作で使用する*str*パラメーターバッファーの最大長。 *Len*パラメーターが指定されていない場合は、 *str*パラメーター全体が使用されます。 *Len*が*sizedest*より大きい場合、 *len*は*sizedest*-1 に設定されます。

*他の*<br/>
別の `HStringReference` オブジェクト。

### <a name="remarks"></a>解説

最初のコンストラクターは、 `HStringReference` パラメーター *str*と同じサイズの新しいオブジェクトを初期化します。

2番目のコンストラクターは、 `HStringReference` サイズがパラメーター *len*で specifeid た新しいオブジェクトを初期化します。

3番目のコンストラクターは、新しい `HStringReference` オブジェクトを*もう一方*のパラメーターの値に初期化し、*その他の*パラメーターを破棄します。

## <a name="hstringreferenceoperator"></a><a name="operator-assign"></a>HStringReference:: operator =

別のオブジェクトの値 `HStringReference` を現在のオブジェクトに移動 `HStringReference` します。

```cpp
HStringReference& operator=(HStringReference&& other) throw()
```

### <a name="parameters"></a>パラメーター

*他の*<br/>
既存の `HStringReference` オブジェクトです。

### <a name="remarks"></a>解説

*既存のオブジェクトの*値が現在のオブジェクトにコピーされ、 `HStringReference` *その他の*オブジェクトが破棄されます。

## <a name="hstringreferenceoperator"></a><a name="operator-equality"></a>HStringReference:: operator = =

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
比較する最初のパラメーター。 *lhs*には、 `HStringReference` オブジェクトまたは hstring ハンドルを指定できます。

*rhs*<br/>
比較する2番目のパラメーター。  *rhs* `HStringReference` オブジェクトまたは hstring ハンドルを指定できます。

### <a name="return-value"></a>戻り値

**`true`***lhs*パラメーターと*rhs*パラメーターが等しい場合は、それ以外の場合は **`false`** 。

## <a name="hstringreferenceoperator"></a><a name="operator-inequality"></a>HStringReference:: operator! =

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
比較する最初のパラメーター。 *lhs*には、 `HStringReference` オブジェクトまたは hstring ハンドルを指定できます。

*rhs*<br/>
比較する2番目のパラメーター。  *rhs* `HStringReference` オブジェクトまたは hstring ハンドルを指定できます。

### <a name="return-value"></a>戻り値

**`true`***lhs*パラメーターと*rhs*パラメーターが等しくない場合は、それ以外の場合は **`false`** 。

## <a name="hstringreferenceoperatorlt"></a><a name="operator-less-than"></a>HStringReference:: operator&lt;

最初のパラメーターが2番目のパラメーターより小さいかどうかを示します。

```cpp
inline bool operator<(
    const HStringReference& lhs,
    const HStringReference& rhs) throw()
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する最初のパラメーター。 *lhs*には、への参照を指定でき `HStringReference` ます。

*rhs*<br/>
比較する2番目のパラメーター。  *rhs*には、への参照を指定でき `HStringReference` ます。

### <a name="return-value"></a>戻り値

**`true`***lhs*パラメーターが*rhs*パラメーターより小さい場合は、それ以外の場合は **`false`** 。
