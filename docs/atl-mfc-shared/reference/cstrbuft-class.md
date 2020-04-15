---
title: クラス
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
ms.openlocfilehash: 84c67aa8ea819f420368a72a2374f800f3d89055
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317643"
---
# <a name="cstrbuft-class"></a>クラス

このクラスは、既存`GetBuffer``ReleaseBuffer``CStringT`のオブジェクトに対するリソースの自動クリーンアップと呼び出しを提供します。

## <a name="syntax"></a>構文

```
template<typename TCharType>
class CStrBufT
```

#### <a name="parameters"></a>パラメーター

*TCharタイプ*<br/>
`CStrBufT`クラスの文字型。 以下のいずれかを指定できます。

- **char** (ANSI 文字列の場合)

- **wchar_t** (Unicode 文字列の場合)

- TCHAR (ANSI および Unicode 文字列の両方の場合)

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|PCXSTR|定数文字列へのポインター。|
|PXSTR|文字列へのポインター。|
|`StringType`|このクラス テンプレートの特殊化によってバッファーを操作する文字列型。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CStrBufT::CStrBufT](#cstrbuft)|文字列バッファー オブジェクトのコンストラクター。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を設定します。](#setlength)|関連付けられた文字列オブジェクトの文字バッファー長を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[::オペレーター PCXSTR](#operator_pcxstr)|関連付けられた文字列オブジェクトの文字バッファーへの**const**ポインターを取得します。|
|[オペレーター PXSTR](#operator_pxstr)|関連付けられた文字列オブジェクトの文字バッファーへのポインターを取得します。|

### <a name="public-constants"></a>パブリック定数

|名前|説明|
|----------|-----------------|
|[CStrBufT::AUTO_LENGTH](#auto_length)|リリース時に文字列の新しい長さを自動的に決定します。|
|[CStrBufT::SET_LENGTH](#set_length)|文字列オブジェクトの長さを GetBuffer 時に設定します。|

## <a name="remarks"></a>解説

このクラスは、[呼](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer)び[出しを](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer)置き換えるためのラッパー クラスとして使用されます[GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength)`ReleaseBuffer`。

主にヘルパー クラスとして設計され`CStrBufT`、開発者が文字列オブジェクトの文字バッファーを使用して、どのように、いつ呼び出`ReleaseBuffer`すかを気にせずに操作する便利な方法を提供します。 これは、例外または複数の終了コード パスの場合、ラッパー オブジェクトがスコープ外に自然に出るためです。を使用して、文字列リソースを解放します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsimpstr.h

## <a name="cstrbuftauto_length"></a><a name="auto_length"></a>CStrBufT::AUTO_LENGTH

リリース時に文字列の新しい長さを自動的に決定します。

```
static const DWORD AUTO_LENGTH = 0x01;
```

### <a name="remarks"></a>解説

リリース時に文字列の新しい長さを自動的に決定します。 文字列は null で終わる必要があります。

## <a name="cstrbuftcstrbuft"></a><a name="cstrbuft"></a>CStrBufT::CStrBufT

バッファー オブジェクトを構築します。

```
CStrBufT(StringType& str, int nMinLength, DWORD dwFlags = AUTO_LENGTH) throw(...);
explicit CStrBufT(StringType& str) throw(...);
```

### <a name="parameters"></a>パラメーター

*Str*<br/>
バッファーに関連付けられている文字列オブジェクト。 通常、開発者は定義済みの`CStrBuf`typedef (TCHAR バリアント)、(char**char**バリアント)、`CStrBufW``CStrBufA`および **(wchar_t**バリアント) を使用します。

*nMin長さ*<br/>
文字バッファーの最小長。

*dwFlags*<br/>
文字列の長さが自動的に決定されるかどうかを判断します。 以下のいずれかを指定できます。

- AUTO_LENGTH文字列の長さは[、CSimpleStringT::リリース](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer)が呼び出されたときに自動的に決定されます。 文字列は null で終わる必要があります。 既定値です。

- 文字列の長さを[SET_LENGTH、文字列](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer)の長さが設定されます。

### <a name="remarks"></a>解説

関連付けられた文字列オブジェクトの文字列バッファーを作成します。 構築中に[、CSimpleStringT::バッファ](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer)または[CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength)が呼び出されます。

コピー コンストラクターは**プライベート**であることに注意してください。

## <a name="cstrbuftoperator-pcxstr"></a><a name="operator_pcxstr"></a>::オペレーター PCXSTR

関連付けられた文字列オブジェクトに格納されている文字に C スタイルの文字列として直接アクセスします。

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>戻り値

文字列のデータへの文字ポインター。

### <a name="remarks"></a>解説

文字列オブジェクトの文字バッファーへのポインターを返します。 文字列オブジェクトの内容は、このポインタでは変更できません。

## <a name="cstrbuftoperator-pxstr"></a><a name="operator_pxstr"></a>オペレーター PXSTR

関連付けられた文字列オブジェクトに格納されている文字に C スタイルの文字列として直接アクセスします。

```
operator PXSTR() throw();
```

### <a name="return-value"></a>戻り値

文字列のデータへの文字ポインター。

### <a name="remarks"></a>解説

文字列オブジェクトの文字バッファーへのポインターを返します。 開発者は、このポインターを使用して文字列オブジェクトの内容を変更できます。

## <a name="cstrbuftpcxstr"></a><a name="pcxstr"></a>CStrBufT::PCXSTR

定数文字列へのポインター。

```
typedef CSimpleStringT<TCharType>::PCXSTR PCXSTR;
```

## <a name="cstrbuftpxstr"></a><a name="pxstr"></a>:PXSTR

文字列へのポインター。

```
typedef CSimpleStringT<TCharType>::PXSTR PXSTR;
```

## <a name="cstrbuftset_length"></a><a name="set_length"></a>CStrBufT::SET_LENGTH

文字列オブジェクトの長さを設定`GetBuffer`します。

```
static const DWORD SET_LENGTH = 0x02;
```

### <a name="remarks"></a>解説

文字列オブジェクトの長さを GetBuffer 時に設定します。

文字列バッファー オブジェクトが構築されるときに[、CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer)と[CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength)が呼び出されるかどうかを判断します。

## <a name="cstrbuftsetlength"></a><a name="setlength"></a>を設定します。

文字バッファーの長さを設定します。

```
void SetLength(int nLength);
```

### <a name="parameters"></a>パラメーター

*nレングス*<br/>
文字列オブジェクトの文字バッファーの新しい長さ。

> [!NOTE]
> のコンストラクターで指定された最小バッファー長以下でなければなりません`CStrBufT`。

### <a name="remarks"></a>解説

バッファー オブジェクトによって表される文字列の長さを設定します。

## <a name="cstrbuftstringtype"></a><a name="stringtype"></a>文字列型

このクラス テンプレートの特殊化によってバッファーを操作する文字列型。

```
typedef CSimpleStringT<TCharType> StringType;
```

### <a name="remarks"></a>解説

`TCharType`は、クラス テンプレートを特化するために使用される文字型です。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)
