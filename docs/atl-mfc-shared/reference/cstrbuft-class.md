---
title: CStrBufT クラス
ms.date: 10/18/2018
f1_keywords:
- CStrBufT
- ATLSIMPSTR/ATL::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::SetLength
- ATLSIMPSTR/ATL::CStrBufT::AUTO_LENGTH
- ATLSIMPSTR/ATL::CStrBufT::SET_LENGTH
helpviewer_keywords:
- strings [C++], custom memory management
- CStrBufT class
- shared classes, CStrBufT
ms.assetid: 6b50fa8f-87e8-4ed4-a229-157ce128710f
ms.openlocfilehash: 4d9d0b403e572d6fdea65355702467c89587cc3a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219080"
---
# <a name="cstrbuft-class"></a>CStrBufT クラス

このクラスは、既存のオブジェクトに対してとを呼び出すための自動リソースクリーンアップを提供 `GetBuffer` し `ReleaseBuffer` `CStringT` ます。

## <a name="syntax"></a>構文

```
template<typename TCharType>
class CStrBufT
```

#### <a name="parameters"></a>パラメーター

*TCharType*<br/>
クラスの文字型 `CStrBufT` 。 以下のいずれかを指定できます。

- **`char`**(ANSI 文字列の場合)

- **`wchar_t`**(Unicode 文字列の場合)

- TCHAR (ANSI 文字列と Unicode 文字列の両方)

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|PCXSTR|定数文字列へのポインター。|
|PXSTR|文字列へのポインター。|
|`StringType`|このクラステンプレートの特殊化によって操作されるバッファーを持つ文字列型。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CStrBufT:: CStrBufT](#cstrbuft)|文字列バッファーオブジェクトのコンストラクター。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CStrBufT:: SetLength](#setlength)|関連付けられている文字列オブジェクトの文字バッファー長を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CStrBufT:: operator PCXSTR](#operator_pcxstr)|**`const`** 関連付けられている文字列オブジェクトの文字バッファーへのポインターを取得します。|
|[CStrBufT:: operator PXSTR](#operator_pxstr)|関連付けられている文字列オブジェクトの文字バッファーへのポインターを取得します。|

### <a name="public-constants"></a>パブリック定数

|名前|説明|
|----------|-----------------|
|[CStrBufT:: AUTO_LENGTH](#auto_length)|リリース時に文字列の新しい長さを自動的に決定します。|
|[CStrBufT:: SET_LENGTH](#set_length)|文字列オブジェクトの長さを GetBuffer 時に設定します。|

## <a name="remarks"></a>解説

このクラスは、 [GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer)および[releasebuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer)への呼び出しや[GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength)とを置き換えるためのラッパークラスとして使用され `ReleaseBuffer` ます。

主にヘルパークラスとして設計されたは、 `CStrBufT` 開発者がを呼び出す方法やタイミングを気にせずに、文字列オブジェクトの文字バッファーを操作するための便利な方法を提供し `ReleaseBuffer` ます。 これは、例外または終了コードパスが複数ある場合に、ラッパーオブジェクトが自然にスコープ外になるためです。デストラクターが文字列リソースを解放する原因になります。

## <a name="requirements"></a>必要条件

**ヘッダー:** atl. h

## <a name="cstrbuftauto_length"></a><a name="auto_length"></a>CStrBufT:: AUTO_LENGTH

リリース時に文字列の新しい長さを自動的に決定します。

```
static const DWORD AUTO_LENGTH = 0x01;
```

### <a name="remarks"></a>解説

リリース時に文字列の新しい長さを自動的に決定します。 文字列は null で終わる必要があります。

## <a name="cstrbuftcstrbuft"></a><a name="cstrbuft"></a>CStrBufT:: CStrBufT

バッファーオブジェクトを構築します。

```
CStrBufT(StringType& str, int nMinLength, DWORD dwFlags = AUTO_LENGTH) throw(...);
explicit CStrBufT(StringType& str) throw(...);
```

### <a name="parameters"></a>パラメーター

*引数*<br/>
バッファーに関連付けられている文字列オブジェクト。 通常、開発者は、 `CStrBuf` (TCHAR variant)、(variant)、(variant) の定義済みの typedef を使用し `CStrBufA` **`char`** `CStrBufW` **`wchar_t`** ます。

*nMinLength*<br/>
文字バッファーの最小長。

*dwFlags*<br/>
文字列の長さを自動的に決定するかどうかを決定します。 以下のいずれかを指定できます。

- AUTO_LENGTH 文字列の長さは、 [CSimpleStringT:: Release](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer)が呼び出されたときに自動的に決定されます。 文字列は null で終わる必要があります。 既定値です。

- [CSimpleStringT:: GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer)が呼び出されたときに SET_LENGTH 文字列の長さが設定されます。

### <a name="remarks"></a>解説

関連付けられている文字列オブジェクトの文字列バッファーを作成します。 構築中に、 [CSimpleStringT:: GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer)または[CSimpleStringT:: GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength)が呼び出されます。

コピーコンストラクターがであることに注意 **`private`** してください。

## <a name="cstrbuftoperator-pcxstr"></a><a name="operator_pcxstr"></a>CStrBufT:: operator PCXSTR

C スタイルの文字列として、関連付けられた文字列オブジェクトに格納されている文字に直接アクセスします。

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>戻り値

文字列のデータへの文字ポインター。

### <a name="remarks"></a>解説

文字列オブジェクトの文字バッファーへのポインターを返すには、この関数を呼び出します。 このポインターを使用して文字列オブジェクトの内容を変更することはできません。

## <a name="cstrbuftoperator-pxstr"></a><a name="operator_pxstr"></a>CStrBufT:: operator PXSTR

C スタイルの文字列として、関連付けられた文字列オブジェクトに格納されている文字に直接アクセスします。

```
operator PXSTR() throw();
```

### <a name="return-value"></a>戻り値

文字列のデータへの文字ポインター。

### <a name="remarks"></a>解説

文字列オブジェクトの文字バッファーへのポインターを返すには、この関数を呼び出します。 開発者は、このポインターを使用して文字列オブジェクトの内容を変更できます。

## <a name="cstrbuftpcxstr"></a><a name="pcxstr"></a>CStrBufT::P CXSTR

定数文字列へのポインター。

```
typedef CSimpleStringT<TCharType>::PCXSTR PCXSTR;
```

## <a name="cstrbuftpxstr"></a><a name="pxstr"></a>CStrBufT::P XSTR

文字列へのポインター。

```
typedef CSimpleStringT<TCharType>::PXSTR PXSTR;
```

## <a name="cstrbuftset_length"></a><a name="set_length"></a>CStrBufT:: SET_LENGTH

時刻に文字列オブジェクトの長さを設定 `GetBuffer` します。

```
static const DWORD SET_LENGTH = 0x02;
```

### <a name="remarks"></a>解説

文字列オブジェクトの長さを GetBuffer 時に設定します。

文字列バッファーオブジェクトが構築されるときに[CSimpleStringT:: GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer)と[CSimpleStringT:: GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength)が呼び出されるかどうかを決定します。

## <a name="cstrbuftsetlength"></a><a name="setlength"></a>CStrBufT:: SetLength

文字バッファーの長さを設定します。

```cpp
void SetLength(int nLength);
```

### <a name="parameters"></a>パラメーター

*nLength*<br/>
文字列オブジェクトの文字バッファーの新しい長さ。

> [!NOTE]
> は、のコンストラクターで指定された最小バッファー長以下である必要があり `CStrBufT` ます。

### <a name="remarks"></a>解説

Buffer オブジェクトによって表される文字列の長さを設定するには、この関数を呼び出します。

## <a name="cstrbuftstringtype"></a><a name="stringtype"></a>CStrBufT:: StringType

このクラステンプレートの特殊化によって操作されるバッファーを持つ文字列型。

```
typedef CSimpleStringT<TCharType> StringType;
```

### <a name="remarks"></a>解説

`TCharType`クラステンプレートを特殊化するために使用される文字型です。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)
