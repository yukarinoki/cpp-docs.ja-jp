---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- COleException
- AFXDISP/COleException
- AFXDISP/COleException::Process
- AFXDISP/COleException::m_sc
helpviewer_keywords:
- COleException [MFC], Process
- COleException [MFC], m_sc
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
ms.openlocfilehash: 737c9e669990f4de6ae18cdc7662c131ad61516f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375008"
---
# <a name="coleexception-class"></a>クラス

OLE 操作に関する例外条件を表します。

## <a name="syntax"></a>構文

```
class COleException : public CException
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[:Pロセス](#process)|キャッチされた例外を OLE リターン コードに変換します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[例外::m_sc](#m_sc)|例外の理由を示す状態コードが含まれています。|

## <a name="remarks"></a>解説

クラス`COleException`には、例外の理由を示す状態コードを保持するパブリック データ メンバーが含まれています。

一般に、オブジェクトを`COleException`直接作成しないでください。代わりに[、AfxThrowOleException を](exception-processing.md#afxthrowoleexception)呼び出す必要があります。

例外の詳細については、「[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md) 」および「[例外: OLE 例外](../../mfc/exceptions-ole-exceptions.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`COleException`

## <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="coleexceptionm_sc"></a><a name="m_sc"></a>例外::m_sc

このデータ メンバは、例外の理由を示す OLE ステータス コードを保持します。

```
SCODE m_sc;
```

### <a name="remarks"></a>解説

この変数の値は[、AfxThrowOleException](exception-processing.md#afxthrowoleexception)によって設定されます。

SCODE の詳細については、Windows SDK[の COM エラー コードの構造](/windows/win32/com/structure-of-com-error-codes)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#22](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]

## <a name="coleexceptionprocess"></a><a name="process"></a>:Pロセス

**処理**メンバー関数を呼び出して、キャッチされた例外を OLE 状態コードに変換します。

```
static SCODE PASCAL Process(const CException* pAnyException);
```

### <a name="parameters"></a>パラメーター

*例外*<br/>
キャッチされた例外へのポインター。

### <a name="return-value"></a>戻り値

OLE ステータス コード。

### <a name="remarks"></a>解説

> [!NOTE]
> この関数は**静的**です。

SCODE の詳細については、Windows SDK[の COM エラー コードの構造](/windows/win32/com/structure-of-com-error-codes)を参照してください。

### <a name="example"></a>例

  [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)の例を参照してください。

## <a name="see-also"></a>関連項目

[MFC サンプル CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[クラスの例外](../../mfc/reference/cexception-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
