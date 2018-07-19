---
title: COleDataObject クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDataObject
- AFXOLE/COleDataObject
- AFXOLE/COleDataObject::COleDataObject
- AFXOLE/COleDataObject::Attach
- AFXOLE/COleDataObject::AttachClipboard
- AFXOLE/COleDataObject::BeginEnumFormats
- AFXOLE/COleDataObject::Detach
- AFXOLE/COleDataObject::GetData
- AFXOLE/COleDataObject::GetFileData
- AFXOLE/COleDataObject::GetGlobalData
- AFXOLE/COleDataObject::GetNextFormat
- AFXOLE/COleDataObject::IsDataAvailable
- AFXOLE/COleDataObject::Release
dev_langs:
- C++
helpviewer_keywords:
- COleDataObject [MFC], COleDataObject
- COleDataObject [MFC], Attach
- COleDataObject [MFC], AttachClipboard
- COleDataObject [MFC], BeginEnumFormats
- COleDataObject [MFC], Detach
- COleDataObject [MFC], GetData
- COleDataObject [MFC], GetFileData
- COleDataObject [MFC], GetGlobalData
- COleDataObject [MFC], GetNextFormat
- COleDataObject [MFC], IsDataAvailable
- COleDataObject [MFC], Release
ms.assetid: d1cc84be-2e1c-4bb3-a8a0-565eb08aaa34
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 33f64902f4636d7933a368e28cac42a27abb440c
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852408"
---
# <a name="coledataobject-class"></a>COleDataObject クラス
クリップボードや OLE 埋め込みアイテムからさまざまなフォーマットのデータを取得するときのデータ転送に使用します。クリップボードからデータを取得するときは、ドラッグ アンド ドロップを使用します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleDataObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleDataObject::COleDataObject](#coledataobject)|`COleDataObject` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleDataObject::Attach](#attach)|指定した OLE データ オブジェクトのアタッチ、`COleDataObject`します。|  
|[COleDataObject::AttachClipboard](#attachclipboard)|クリップボード上のデータ オブジェクトをアタッチします。|  
|[COleDataObject::BeginEnumFormats](#beginenumformats)|1 つまたは複数後続準備`GetNextFormat`呼び出し。|  
|[COleDataObject::Detach](#detach)|関連付けられているデタッチ`IDataObject`オブジェクト。|  
|[COleDataObject::GetData](#getdata)|指定された形式で、アタッチされた OLE データ オブジェクトからのデータをコピーします。|  
|[COleDataObject::GetFileData](#getfiledata)|接続されている OLE データ オブジェクトからデータをコピー、`CFile`指定された形式でのポインター。|  
|[COleDataObject::GetGlobalData](#getglobaldata)|接続されている OLE データ オブジェクトからデータをコピー、`HGLOBAL`指定された形式。|  
|[COleDataObject::GetNextFormat](#getnextformat)|次のデータ形式を返します。|  
|[COleDataObject::IsDataAvailable](#isdataavailable)|データが指定された形式で使用できるかどうかを確認します。|  
|[COleDataObject::Release](#release)|デタッチし、関連付けられているリリース`IDataObject`オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 `COleDataObject` 基本クラスはありません。  
  
 これらの種類データ転送にはには、ソースおよび変換先が含まれます。 オブジェクトとしてデータ ソースが実装されている、 [COleDataSource](../../mfc/reference/coledatasource-class.md)クラス。 転送先アプリケーションがデータがドロップを持っているかのオブジェクト、クリップボードから貼り付け操作を実行するよう指示されますたびに、`COleDataObject`クラスを作成する必要があります。  
  
 このクラスでは、指定された形式でデータが存在するかどうかを判断することができます。 使用可能なデータ形式を列挙することもまたは特定の形式が使用できるかどうかを確認し、希望の形式でデータを取得できます。 使用など、いくつかの異なる方法でオブジェクトの取得を行うことができます、 [CFile](../../mfc/reference/cfile-class.md)HGLOBAL、または`STGMEDIUM`構造体。  
  
 詳細については、次を参照してください。、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Windows SDK の構造体。  
  
 詳細については、アプリケーションでデータ オブジェクトを使用して、記事を参照してください。[データ オブジェクトとデータ ソース (OLE)](../../mfc/data-objects-and-data-sources-ole.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `COleDataObject`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxole.h  
  
##  <a name="attach"></a>  COleDataObject::Attach  
 関連付けるには、この関数を呼び出して、 `COleDataObject` OLE データ オブジェクトを持つオブジェクト。  
  
```  
void Attach(
    LPDATAOBJECT lpDataObject,  
    BOOL bAutoRelease = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpDataObject*  
 OLE データ オブジェクトへのポインター。  
  
 *bAutoRelease*  
 OLE のデータ オブジェクトにする場合は TRUE。 時に解放される、`COleDataObject`オブジェクトが破棄された場合はそれ以外の場合は FALSE。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) Windows SDK に含まれています。  
  
##  <a name="attachclipboard"></a>  COleDataObject::AttachClipboard  
 現在クリップボード上にあるデータ オブジェクトをアタッチするには、この関数を呼び出し、`COleDataObject`オブジェクト。  
  
```  
BOOL AttachClipboard();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
  
> [!NOTE]
>  この関数を呼び出すことでは、このデータ オブジェクトが解放されるまでに、クリップボードをロックします。 データ オブジェクトのデストラクターで解放、`COleDataObject`します。 詳細については、次を参照してください。 [OpenClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649048)と[CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) Win32 ドキュメントにします。  
  
##  <a name="beginenumformats"></a>  COleDataObject::BeginEnumFormats  
 後続の呼び出しを準備するには、この関数を呼び出す`GetNextFormat`項目からのデータ形式の一覧を取得するためです。  
  
```  
void BeginEnumFormats();
```  
  
### <a name="remarks"></a>Remarks  
 呼び出しの後に`BeginEnumFormats`、最初にこのデータ オブジェクトでサポートされる形式の位置を保存します。 連続して呼び出す`GetNextFormat`データ オブジェクトで使用可能な形式の一覧を列挙します。  
  
 指定された形式でデータの可用性を確認するには使用[COleDataObject::IsDataAvailable](#isdataavailable)します。  
  
 詳細については、次を参照してください。 [IDataObject::EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979) Windows SDK に含まれています。  
  
##  <a name="coledataobject"></a>  COleDataObject::COleDataObject  
 `COleDataObject` オブジェクトを構築します。  
  
```  
COleDataObject();
```  
  
### <a name="remarks"></a>Remarks  
 呼び出し[COleDataObject::Attach](#attach)または[COleDataObject::AttachClipboard](#attachclipboard)他を呼び出す前に行う必要がある`COleDataObject`関数。  
  
> [!NOTE]
>  ポインターをドラッグ アンド ドロップ ハンドラーのパラメーターの 1 つは、 `COleDataObject`、ドラッグ アンド ドロップをサポートするためにこのコンス トラクターを呼び出す必要はありません。  
  
##  <a name="detach"></a>  COleDataObject::Detach  
 デタッチするには、この関数を呼び出し、`COleDataObject`オブジェクトからのデータ オブジェクトを解放しないままその関連付けられた OLE データ オブジェクト。  
  
```  
LPDATAOBJECT Detach();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされた OLE データ オブジェクトへのポインター。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getdata"></a>  COleDataObject::GetData  
 この関数では、指定された形式で項目からデータを取得します。  
  
```  
BOOL GetData(
    CLIPFORMAT cfFormat,  
    LPSTGMEDIUM lpStgMedium,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *cfFormat*  
 データが返される形式です。 このパラメーターは、定義済みのクリップボード形式またはネイティブの Windows で返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数。  
  
 *lpStgMedium*  
 指す、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)データを受け取る構造体。  
  
 *lpFormatEtc*  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)データが返される形式を記述する構造体。 指定されたクリップボード形式の書式の追加情報を指定する場合、このパラメーターの値を指定*cfFormat*します。 他のフィールドの既定値が使用が NULL の場合、`FORMATETC`構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431)、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)、と[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK に含まれています。  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)Windows SDK に含まれています。  
  
##  <a name="getfiledata"></a>  COleDataObject::GetFileData  
 作成するには、この関数を呼び出す、`CFile`または`CFile`-派生オブジェクトに指定された形式でデータを取得して、`CFile`ポインター。  
  
```  
CFile* GetFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *cfFormat*  
 データが返される形式です。 このパラメーターは、定義済みのクリップボード形式またはネイティブの Windows で返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数。  
  
 *lpFormatEtc*  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)データが返される形式を記述する構造体。 指定されたクリップボード形式の書式の追加情報を指定する場合、このパラメーターの値を指定*cfFormat*します。 他のフィールドの既定値が使用が NULL の場合、`FORMATETC`構造体。  
  
### <a name="return-value"></a>戻り値  
 新しいポインター`CFile`または`CFile`-成功。 それ以外の場合に NULL の場合は、データを含むオブジェクトを派生します。  
  
### <a name="remarks"></a>Remarks  
 データが格納されている中、によって、戻り値によって示される実際の型があります`CFile`、 `CSharedFile`、または`COleStreamFile`します。  
  
> [!NOTE]
>  `CFile`この関数の戻り値によってアクセスされるオブジェクトには、呼び出し元が所有します。 呼び出し元の責任は**削除**、`CFile`をファイルを閉じる。  
  
 詳細については、次を参照してください。 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK に含まれています。  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)Windows SDK に含まれています。  
  
##  <a name="getglobaldata"></a>  COleDataObject::GetGlobalData  
 グローバル メモリ ブロックを割り当てると、HGLOBAL に指定された形式でデータを取得するこの関数を呼び出します。  
  
```  
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *cfFormat*  
 データが返される形式です。 このパラメーターは、定義済みのクリップボード形式またはネイティブの Windows で返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数。  
  
 *lpFormatEtc*  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)データが返される形式を記述する構造体。 指定されたクリップボード形式の書式の追加情報を指定する場合、このパラメーターの値を指定*cfFormat*します。 他のフィールドの既定値が使用が NULL の場合、`FORMATETC`構造体。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、データを格納しているグローバル メモリ ブロックのハンドルそれ以外の場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK に含まれています。  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)Windows SDK に含まれています。  
  
##  <a name="getnextformat"></a>  COleDataObject::GetNextFormat  
 項目からデータを取得するために使用可能なすべての形式を取得するには、繰り返しには、この関数を呼び出します。  
  
```  
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpFormatEtc*  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)関数呼び出しが戻るときの書式情報を受け取る。  
  
### <a name="return-value"></a>戻り値  
 別の形式が使用可能な場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 呼び出しの後に[COleDataObject::BeginEnumFormats](#beginenumformats)、最初にこのデータ オブジェクトでサポートされる形式の位置を保存します。 連続して呼び出す`GetNextFormat`データ オブジェクトで使用可能な形式の一覧を列挙します。 これらの関数を使用して、使用可能な形式の一覧します。  
  
 指定した形式の可用性を確認するには、呼び出し[COleDataObject::IsDataAvailable](#isdataavailable)します。  
  
 詳細については、次を参照してください。 [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) Windows SDK に含まれています。  
  
##  <a name="isdataavailable"></a>  COleDataObject::IsDataAvailable  
 この関数では、特定の形式が OLE 項目からデータを取得するために使用できるかを判断します。  
  
```  
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *cfFormat*  
 によって示される構造体で使用するクリップボード データ形式*lpFormatEtc*します。 このパラメーターは、定義済みのクリップボード形式またはネイティブの Windows で返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数。  
  
 *lpFormatEtc*  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)目的の形式を記述する構造体。 指定されたクリップボード形式の書式の追加情報を指定する場合にのみ、このパラメーターの値を指定*cfFormat*します。 他のフィールドの既定値が使用が NULL の場合、`FORMATETC`構造体。  
  
### <a name="return-value"></a>戻り値  
 指定した形式でデータがある場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数は呼び出しの前に`GetData`、 `GetFileData`、または`GetGlobalData`します。  
  
 詳細については、次を参照してください。 [IDataObject::QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637)と[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK に含まれています。  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例をご覧ください[CRichEditView::QueryAcceptData](../../mfc/reference/cricheditview-class.md#queryacceptdata)します。  
  
##  <a name="release"></a>  COleDataObject::Release  
 所有権を解放するには、この関数を呼び出して、 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421)が以前関連付けられているオブジェクト、`COleDataObject`オブジェクト。  
  
```  
void Release();
```  
  
### <a name="remarks"></a>Remarks  
 `IDataObject`に関連付けられているが、`COleDataObject`呼び出して`Attach`または`AttachClipboard`明示的にまたは framework。 場合、 *bAutoRelease*パラメーターの`Attach`、false、`IDataObject`オブジェクトは解放されません。 この場合、呼び出し元が解放、`IDataObject`呼び出して[:release](http://msdn.microsoft.com/library/windows/desktop/ms682317)します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [MFC サンプルの OCLIENT](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDataSource クラス](../../mfc/reference/coledatasource-class.md)   
 [COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)   
 [COleServerItem クラス](../../mfc/reference/coleserveritem-class.md)
