---
title: COleDispatchException クラス
ms.date: 11/04/2016
f1_keywords:
- COleDispatchException
- AFXDISP/COleDispatchException
- AFXDISP/COleDispatchException::m_dwHelpContext
- AFXDISP/COleDispatchException::m_strDescription
- AFXDISP/COleDispatchException::m_strHelpFile
- AFXDISP/COleDispatchException::m_strSource
- AFXDISP/COleDispatchException::m_wCode
helpviewer_keywords:
- COleDispatchException [MFC], m_dwHelpContext
- COleDispatchException [MFC], m_strDescription
- COleDispatchException [MFC], m_strHelpFile
- COleDispatchException [MFC], m_strSource
- COleDispatchException [MFC], m_wCode
ms.assetid: 0e95c8be-e21a-490c-99ec-181c6a9a26d0
ms.openlocfilehash: 4572b639b757569d8e3cfa731f99c123762f3900
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375062"
---
# <a name="coledispatchexception-class"></a>COleDispatchException クラス

OLE オートメーションの主要部分である OLE `IDispatch` インターフェイス固有の例外を処理します。

## <a name="syntax"></a>構文

```
class COleDispatchException : public CException
```

## <a name="members"></a>メンバー

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[例外::m_dwHelpContext](#m_dwhelpcontext)|エラーのヘルプ コンテキスト。|
|[m_strDescription を指定します。](#m_strdescription)|口頭でのエラーの説明。|
|[を呼び出します m_strHelpFile。](#m_strhelpfile)|で使用するヘルプ`m_dwHelpContext`ファイル。|
|[例外::m_strSource](#m_strsource)|例外を生成したアプリケーション。|
|[を呼び出します m_wCode。](#m_wcode)|`IDispatch`-固有のエラー コード。|

## <a name="remarks"></a>解説

基本クラスから派生した他の`CException`例外クラスと同様`COleDispatchException`に、THROW、THROW_LAST、try、CATCH、AND_CATCH、およびEND_CATCHマクロと共に使用できます。

一般的に、オブジェクトを作成してスローするには[、AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception)を呼び出す`COleDispatchException`必要があります。

例外の詳細については、「[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md) 」および「[例外: OLE 例外](../../mfc/exceptions-ole-exceptions.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`COleDispatchException`

## <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="coledispatchexceptionm_dwhelpcontext"></a><a name="m_dwhelpcontext"></a>例外::m_dwHelpContext

アプリケーションのヘルプ (.HLP) ファイル。

```
DWORD m_dwHelpContext;
```

### <a name="remarks"></a>解説

このメンバーは、例外がスローされたときに関数[AfxThrowOleDispatch 例外](exception-processing.md#afxthrowoledispatchexception)によって設定されます。

### <a name="example"></a>例

  [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)の例を参照してください。

## <a name="coledispatchexceptionm_strdescription"></a><a name="m_strdescription"></a>m_strDescription を指定します。

"ディスクがいっぱいです" などの言葉によるエラーの説明が含まれています。

```
CString m_strDescription;
```

### <a name="remarks"></a>解説

このメンバーは、例外がスローされたときに関数[AfxThrowOleDispatch 例外](exception-processing.md#afxthrowoledispatchexception)によって設定されます。

### <a name="example"></a>例

  [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)の例を参照してください。

## <a name="coledispatchexceptionm_strhelpfile"></a><a name="m_strhelpfile"></a>を呼び出します m_strHelpFile。

フレームワークは、アプリケーションのヘルプ ファイルの名前をこの文字列で埋めます。

```
CString m_strHelpFile;
```

## <a name="coledispatchexceptionm_strsource"></a><a name="m_strsource"></a>例外::m_strSource

フレームワークは、例外を生成したアプリケーションの名前をこの文字列で埋めます。

```
CString m_strSource;
```

### <a name="example"></a>例

  [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)の例を参照してください。

## <a name="coledispatchexceptionm_wcode"></a><a name="m_wcode"></a>を呼び出します m_wCode。

アプリケーションに固有のエラー コードが含まれています。

```
WORD m_wCode;
```

### <a name="remarks"></a>解説

このメンバーは、例外がスローされたときに関数[AfxThrowOleDispatch 例外](exception-processing.md#afxthrowoledispatchexception)によって設定されます。

## <a name="see-also"></a>関連項目

[MFC サンプル CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[クラスの例外](../../mfc/reference/cexception-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラスをディスパッチします。](../../mfc/reference/coledispatchdriver-class.md)<br/>
[クラス](../../mfc/reference/coleexception-class.md)
