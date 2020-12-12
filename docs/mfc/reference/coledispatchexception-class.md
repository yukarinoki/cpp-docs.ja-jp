---
description: '詳細情報: COleDispatchException クラス'
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
ms.openlocfilehash: 39d8c4652f49b721e5f94c05319e5c1adad07269
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227209"
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
|[COleDispatchException:: m_dwHelpContext](#m_dwhelpcontext)|エラーのヘルプコンテキスト。|
|[COleDispatchException:: m_strDescription](#m_strdescription)|口頭でのエラーの説明。|
|[COleDispatchException:: m_strHelpFile](#m_strhelpfile)|で使用するヘルプファイル `m_dwHelpContext` 。|
|[COleDispatchException:: m_strSource](#m_strsource)|例外を生成したアプリケーション。|
|[COleDispatchException:: m_wCode](#m_wcode)|`IDispatch`-固有のエラーコード。|

## <a name="remarks"></a>解説

基本クラスから派生した他の例外クラスと同様に `CException` 、は `COleDispatchException` THROW、THROW_LAST、TRY、CATCH、AND_CATCH、および END_CATCH マクロと共に使用できます。

一般に、オブジェクトを作成してスローするには、 [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) を呼び出す必要があり `COleDispatchException` ます。

例外の詳細については、「 [例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md) 」および「 [例外: OLE 例外](../../mfc/exceptions-ole-exceptions.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`COleDispatchException`

## <a name="requirements"></a>要件

**ヘッダー :** afxdisp.h

## <a name="coledispatchexceptionm_dwhelpcontext"></a><a name="m_dwhelpcontext"></a> COleDispatchException:: m_dwHelpContext

アプリケーションのヘルプのヘルプコンテキストを識別します (「」を参照してください。HLP) ファイル。

```
DWORD m_dwHelpContext;
```

### <a name="remarks"></a>解説

このメンバーは、例外がスローされたときに、関数 [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) によって設定されます。

### <a name="example"></a>例

  [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)の例を参照してください。

## <a name="coledispatchexceptionm_strdescription"></a><a name="m_strdescription"></a> COleDispatchException:: m_strDescription

"ディスクがいっぱいです" などの音声エラーの説明が含まれています。

```
CString m_strDescription;
```

### <a name="remarks"></a>解説

このメンバーは、例外がスローされたときに、関数 [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) によって設定されます。

### <a name="example"></a>例

  [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)の例を参照してください。

## <a name="coledispatchexceptionm_strhelpfile"></a><a name="m_strhelpfile"></a> COleDispatchException:: m_strHelpFile

フレームワークは、この文字列にアプリケーションのヘルプファイルの名前を入力します。

```
CString m_strHelpFile;
```

## <a name="coledispatchexceptionm_strsource"></a><a name="m_strsource"></a> COleDispatchException:: m_strSource

フレームワークは、この文字列に、例外を生成したアプリケーションの名前を入力します。

```
CString m_strSource;
```

### <a name="example"></a>例

  [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)の例を参照してください。

## <a name="coledispatchexceptionm_wcode"></a><a name="m_wcode"></a> COleDispatchException:: m_wCode

には、アプリケーション固有のエラーコードが含まれています。

```
WORD m_wCode;
```

### <a name="remarks"></a>解説

このメンバーは、例外がスローされたときに、関数 [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) によって設定されます。

## <a name="see-also"></a>関連項目

[MFC のサンプル CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[CException クラス](../../mfc/reference/cexception-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleDispatchDriver クラス](../../mfc/reference/coledispatchdriver-class.md)<br/>
[COleException クラス](../../mfc/reference/coleexception-class.md)
