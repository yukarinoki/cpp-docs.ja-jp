---
description: '詳細情報: CFixedStringT クラス'
title: CFixedStringT クラス
ms.date: 03/27/2019
f1_keywords:
- CFixedStringT
- CSTRINGT/ATL::CFixedStringT
- CSTRINGT/ATL::CFixedStringT::CFixedStringT
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
ms.openlocfilehash: a613716364318ced140709d2b33e9d9c4299af0b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166837"
---
# <a name="cfixedstringt-class"></a>CFixedStringT クラス

このクラスは、固定文字バッファーを持つ文字列オブジェクトを表します。

## <a name="syntax"></a>構文

```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```

#### <a name="parameters"></a>パラメーター

*StringType*<br/>
固定文字列オブジェクトの基本クラスとして使用され、任意のベース型にすることができ `CStringT` ます。 例として、、、などがあり `CString` `CStringA` `CStringW` ます。

*t_nChars*<br/>
バッファーに格納されている文字数。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CFixedStringT:: CFixedStringT](#cfixedstringt)|文字列オブジェクトのコンストラクター。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CFixedStringT:: operator =](#operator_eq)|オブジェクトに新しい値を割り当て `CFixedStringT` ます。|

## <a name="remarks"></a>解説

このクラスは、に基づくカスタム文字列クラスの例です `CStringT` 。 似ていますが、2つのクラスは実装によって異なります。 との主 `CFixedStringT` な違い `CStringT` は次のとおりです。

- 初期の文字バッファーは、オブジェクトの一部として割り当てられ、サイズ *t_nChars* します。 これにより、オブジェクトは、 `CFixedString` パフォーマンスのために連続するメモリチャンクを占有できます。 ただし、オブジェクトの内容が `CFixedStringT` *t_nChars* を超えると、バッファーは動的に割り当てられます。

- オブジェクトの文字バッファー `CFixedStringT` は、常に同じ長さ ( *t_nChars*) です。 オブジェクトのバッファーサイズに制限はありません `CStringT` 。

- のメモリマネージャー `CFixedStringT` は、2つ以上のオブジェクト間の [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) オブジェクトの共有が許可されないようにカスタマイズされてい `CFixedStringT` ます。 `CStringT` オブジェクトには、この制限はありません。

`CFixedStringT`一般的な文字列オブジェクトのおよびメモリ管理のカスタマイズの詳細については、「[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`IAtlStringMgr`

`StringType`

`CFixedStringMgr`

`CFixedStringT`

## <a name="requirements"></a>要件

**ヘッダー:** cstringt

## <a name="cfixedstringtcfixedstringt"></a><a name="cfixedstringt"></a> CFixedStringT:: CFixedStringT

`CFixedStringT` オブジェクトを構築します。

```
CFixedStringT() throw();
explicit CFixedStringT(IAtlStringMgr* pStringMgr) throw();
CFixedStringT(const CFixedStringT<StringType, t_nChars>& strSrc);
CFixedStringT(const StringType& strSrc);
CFixedStringT(const StringType::XCHAR* pszSrc);
explicit CFixedStringT(const StringType::YCHAR* pszSrc);
explicit CFixedStringT(const unsigned char* pszSrc);
```

### <a name="parameters"></a>パラメーター

*pszSrc*<br/>
このオブジェクトにコピーされる null で終わる文字列 `CFixedStringT` 。

*strSrc*<br/>
`CFixedStringT`このオブジェクトにコピーされる既存のオブジェクト `CFixedStringT` 。

*pStringMgr*<br/>
オブジェクトのメモリマネージャーへのポインター `CFixedStringT` 。 とのメモリ管理の詳細について `IAtlStringMgr` `CFixedStringT` は、「 [メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)」を参照してください。

### <a name="remarks"></a>解説

コンストラクターは、割り当てられた新しいストレージに入力データをコピーするので、メモリ例外が発生する可能性があることに注意する必要があります。 これらのコンストラクターの一部は、変換関数として機能します。

## <a name="cfixedstringtoperator-"></a><a name="operator_eq"></a> CFixedStringT:: operator =

`CFixedStringT`新しいデータで既存のオブジェクトを再初期化します。

```
CFixedStringT<StringType, t_nChars>& operator=(
    const CFixedStringT<StringType, t_nChars>& strSrc);
CFixedStringT<StringType, t_nChars>& operator=(const char* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const wchar_t* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const unsigned char* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const StringType& strSrc);
```

### <a name="parameters"></a>パラメーター

*pszSrc*<br/>
このオブジェクトにコピーされる null で終わる文字列 `CFixedStringT` 。

*strSrc*<br/>
`CFixedStringT`このオブジェクトにコピーされる既存の `CFixedStringT` 。

### <a name="remarks"></a>解説

新しいストレージは多くの場合、結果のオブジェクトを保持するために割り当てられるため、代入演算子を使用するたびにメモリ例外が発生する可能性があることに注意してください `CFixedStringT` 。

## <a name="see-also"></a>関連項目

[CStringT クラス](../../atl-mfc-shared/reference/cstringt-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)
