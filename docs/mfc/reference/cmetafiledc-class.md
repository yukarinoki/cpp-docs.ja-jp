---
title: CMetaFileDC クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMetaFileDC
- AFXEXT/CMetaFileDC
- AFXEXT/CMetaFileDC::CMetaFileDC
- AFXEXT/CMetaFileDC::Close
- AFXEXT/CMetaFileDC::CloseEnhanced
- AFXEXT/CMetaFileDC::Create
- AFXEXT/CMetaFileDC::CreateEnhanced
dev_langs:
- C++
helpviewer_keywords:
- CMetaFileDC [MFC], CMetaFileDC
- CMetaFileDC [MFC], Close
- CMetaFileDC [MFC], CloseEnhanced
- CMetaFileDC [MFC], Create
- CMetaFileDC [MFC], CreateEnhanced
ms.assetid: ffce60fa-4181-4d46-9832-25e46fad4db4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a588a848e7964a70f47d4cf29a5f5ef2741881d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368155"
---
# <a name="cmetafiledc-class"></a>CMetaFileDC クラス
イメージやテキストを自由に作成するための一連のグラフィック デバイス インターフェイス (GDI) コマンドを含む Windows のメタファイルを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMetaFileDC : public CDC  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMetaFileDC::CMetaFileDC](#cmetafiledc)|`CMetaFileDC` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMetaFileDC::Close](#close)|デバイス コンテキストを閉じ、メタファイル ハンドルを作成します。|  
|[CMetaFileDC::CloseEnhanced](#closeenhanced)|拡張メタファイル デバイス コンテキストを閉じるし、拡張メタファイル ハンドルを作成します。|  
|[CMetaFileDC::Create](#create)|Windows のメタファイル デバイス コンテキストを作成しにアタッチ、`CMetaFileDC`オブジェクト。|  
|[CMetaFileDC::CreateEnhanced](#createenhanced)|拡張形式メタファイルのメタファイル デバイス コンテキストを作成します。|  
  
## <a name="remarks"></a>コメント  
 Windows のメタファイルを実装するには、最初に作成、`CMetaFileDC`オブジェクト。 呼び出す、`CMetaFileDC`コンス トラクターを呼び出して、[作成](#create)メンバー関数は、Windows メタファイル デバイス コンテキストを作成し、それにアタッチ、`CMetaFileDC`オブジェクト。  
  
 次に送信、`CMetaFileDC`オブジェクトのシーケンス`CDC`に再生する GDI コマンド。 ように、出力を作成した GDI コマンドのみ`MoveTo`と`LineTo`、使用できます。  
  
 メタファイルに必要なコマンドを送信した後、**閉じる**メンバー関数は、メタファイル デバイス コンテキストを閉じ、メタファイル ハンドルを返します。 破棄、`CMetaFileDC`オブジェクト。  
  
 [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile)メタファイルを繰り返し再生するメタファイルのハンドルを使用し、ことができます。 メタファイルも操作できる Windows 関数など[CopyMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183480)メタファイルをディスクにコピーします。  
  
 メタファイルを不要になったときにメモリから削除、 [DeleteMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183537) Windows の機能です。  
  
 実装することも、`CMetaFileDC`オブジェクトを処理できるようにの両方の呼び出しの出力し、GDI の呼び出しをなど属性`GetTextExtent`です。 このようなメタファイルより柔軟性がおよびより簡単に再利用できる全般 GDI コードでは、多くの場合、出力と属性の呼び出しの組み合わせから成ります。 `CMetaFileDC`クラスは 2 つのデバイス コンテキストを継承`m_hDC`と`m_hAttribDC`から`CDC`です。 `m_hDC`デバイス コンテキストでは、すべてを処理[CDC](../../mfc/reference/cdc-class.md) GDI の呼び出しの出力と`m_hAttribDC`デバイス コンテキストでは、すべてを処理`CDC`GDI 属性呼び出しです。 通常、これらの 2 つのデバイス コンテキストでは、同じデバイスを参照してください。 場合、 `CMetaFileDC`、DC の属性に設定されている**NULL**既定です。  
  
 画面、プリンター、または、メタファイル以外のデバイスへのポインターを呼び出す 2 つ目のデバイス コンテキストを作成、`SetAttribDC`メンバー関数で新しいデバイス コンテキストを結び付けるため`m_hAttribDC`です。 GDI 呼び出しについては、新規に送られますようになりました`m_hAttribDC`です。 出力 GDI 呼び出しに移動する`m_hDC`メタファイルを表します。  
  
 詳細については`CMetaFileDC`を参照してください[デバイス コンテキスト](../../mfc/device-contexts.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CMetaFileDC`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
##  <a name="close"></a>  CMetaFileDC::Close  
 メタファイル デバイス コンテキストを閉じ、メタファイルを使用して、再生に使用できる Windows メタファイル ハンドルを作成、 [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile)メンバー関数。  
  
```  
HMETAFILE Close();
```  
  
### <a name="return-value"></a>戻り値  
 有効な**終了した**関数が成功した場合**NULL**です。  
  
### <a name="remarks"></a>コメント  
 Windows のメタファイル ハンドルなどの Windows の関数とメタファイルの操作にも使用できます[CopyMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183480)です。  
  
 使用後に、Windows を呼び出すことによって、メタファイルは削除[DeleteMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183537)関数。  
  
##  <a name="closeenhanced"></a>  CMetaFileDC::CloseEnhanced  
 拡張メタファイル デバイス コンテキストを閉じて、拡張メタファイルを識別するハンドルを返します。  
  
```  
HENHMETAFILE CloseEnhanced();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、拡張メタファイルのハンドルそれ以外の場合**NULL**です。  
  
### <a name="remarks"></a>コメント  
 アプリケーションは、次のタスクを実行するのにこの関数によって返された拡張メタファイル ハンドルを使用できます。  
  
-   拡張メタファイルに格納されている画像を表示します。  
  
-   拡張メタファイルのコピーを作成します。  
  
-   列挙、編集、または拡張メタファイル内の個々 のレコードのコピー  
  
-   拡張メタファイル ヘッダーからメタファイルの内容の説明 (オプション) を取得します。  
  
-   拡張メタファイルのヘッダーのコピーを取得します。  
  
-   拡張メタファイルのバイナリのコピーを取得します。  
  
-   オプションのパレットで色を列挙します。  
  
-   拡張形式メタファイルを Windows メタファイルに変換します。  
  
 アプリケーションには、拡張メタファイルのハンドルが必要がなくなりには、win32 ハンドルを解除する必要が**DeleteEnhMetaFile**関数。  
  
##  <a name="cmetafiledc"></a>  CMetaFileDC::CMetaFileDC  
 構築、 `CMetaFileDC` 2 つのステップ内のオブジェクト。  
  
```  
CMetaFileDC();
```  
  
### <a name="remarks"></a>コメント  
 最初に、呼び出す`CMetaFileDC`を呼び出す**作成**、Windows のメタファイル デバイス コンテキストを作成およびにアタッチする、`CMetaFileDC`オブジェクト。  
  
##  <a name="create"></a>  CMetaFileDC::Create  
 構築、 `CMetaFileDC` 2 つのステップ内のオブジェクト。  
  
```  
BOOL Create(LPCTSTR lpszFilename = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *場合*  
 Null で終わる文字列へのポインター。 作成するメタファイルのファイル名を指定します。 場合*場合*は**NULL**、新しいメモリ内メタファイルを作成します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 最初に、コンス トラクターを呼び出す`CMetaFileDC`を呼び出す**作成**、Windows のメタファイル デバイス コンテキストを作成およびにアタッチする、`CMetaFileDC`オブジェクト。  
  
##  <a name="createenhanced"></a>  CMetaFileDC::CreateEnhanced  
 拡張形式メタファイルのデバイス コンテキストを作成します。  
  
```  
BOOL CreateEnhanced(
    CDC* pDCRef,  
    LPCTSTR lpszFileName,  
    LPCRECT lpBounds,  
    LPCTSTR lpszDescription);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDCRef`  
 拡張メタファイル用のデバイスの参照を識別します。  
  
 `lpszFileName`  
 Null で終わる文字列へのポインター。 作成する拡張メタファイルのファイル名を指定します。 このパラメーターは、する場合**NULL**、拡張メタファイルはメモリ ベースとその内容が失われたオブジェクトが破棄されるとき、または Win32 **DeleteEnhMetaFile**関数が呼び出されます。  
  
 `lpBounds`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)データ構造体、または[CRect](../../atl-mfc-shared/reference/crect-class.md)内のディメンションを指定するオブジェクト**HIMETRIC**に格納される画像の (.01 ミリメートル単位) の単位、拡張メタファイル。  
  
 `lpszDescription`  
 画像のタイトルと同様に、画像を作成したアプリケーションの名前を指定する 0 で終わる文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、拡張メタファイル デバイス コンテキストのハンドルそれ以外の場合**NULL**です。  
  
### <a name="remarks"></a>コメント  
 この DC は、デバイスに依存しない画像を格納できます。  
  
 Windows で識別される参照デバイスを使用して、`pDCRef`解像度と、デバイスを画像表示されていた元の単位を記録するパラメーターです。 場合、`pDCRef`パラメーターは**NULL**参照を現在のディスプレイ デバイスを使用します。  
  
 左と上のメンバー、`RECT`データ構造体を指す、`lpBounds`パラメーターより小さくなければなりません右および下メンバーをそれぞれします。 図では、四角形の端に沿ったポイントが含まれています。 場合`lpBounds`は**NULL**、グラフィックス デバイス インターフェイス (GDI) は、アプリケーションによって描画された画像を囲む最も小さな四角形のサイズを計算します。 `lpBounds`可能な限り、パラメーターを指定する必要があります。  
  
 文字列を指す、`lpszDescription`パラメーターは、アプリケーションの名前と画像の名前の間での null 文字を含める必要があり、2 つの null 文字で終了する必要があります: たとえば、"XYZ グラフィックス Editor\0Bald Eagle\0\0、"\0 が、null を表します文字があります。 場合`lpszDescription`は**NULL**、拡張メタファイルのヘッダーに対応するエントリがありません。  
  
 アプリケーションでは、この関数によって作成されたドメイン コント ローラーを使用して拡張メタファイルにグラフィックスの画像を保存します。 このドメイン コント ローラーを識別するハンドルは、任意の GDI 関数に渡されることができます。  
  
 アプリケーションは、拡張メタファイルに画像を保存した後、画像を表示できるすべての出力デバイスで呼び出すことによって、`CDC::PlayMetaFile`関数。 画像を表示するには、Windows では、四角形によって示される、`lpBounds`パラメーターと位置し、スケールの画像を参照するデバイスからの解像度のデータ。 この関数によって返されるデバイス コンテキストには、任意の新しい DC に関連付けられている同じ既定の属性が含まれています。  
  
 アプリケーションは、Win32 を使用する必要があります**GetWinMetaFileBits**拡張メタファイルを以前の Windows メタファイル形式に変換する関数。  
  
 拡張メタファイルのファイル名を使用する必要があります、します。EMF 拡張機能です。  
  
## <a name="see-also"></a>関連項目  
 [CDC クラス](../../mfc/reference/cdc-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



