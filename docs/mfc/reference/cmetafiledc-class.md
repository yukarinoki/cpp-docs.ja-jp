---
title: CMetaFileDC クラス |Microsoft Docs
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
ms.openlocfilehash: fb2fd794798f96cceca893df4a69dc888196d9a6
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197004"
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
|[CMetaFileDC::Close](#close)|デバイス コンテキストを閉じて、メタファイルのハンドルを作成します。|  
|[CMetaFileDC::CloseEnhanced](#closeenhanced)|拡張メタファイル デバイス コンテキストを閉じ、拡張メタファイルのハンドルを作成します。|  
|[CMetaFileDC::Create](#create)|Windows メタファイル デバイス コンテキストを作成しにアタッチします、`CMetaFileDC`オブジェクト。|  
|[CMetaFileDC::CreateEnhanced](#createenhanced)|拡張形式メタファイルのメタファイル デバイス コンテキストを作成します。|  
  
## <a name="remarks"></a>Remarks  
 Windows メタファイルを実装するために最初に作成、`CMetaFileDC`オブジェクト。 呼び出す、`CMetaFileDC`コンス トラクターを呼び出して、[作成](#create)メンバー関数は、Windows メタファイル デバイス コンテキストを作成しにアタッチします、`CMetaFileDC`オブジェクト。  
  
 次に送信、`CMetaFileDC`を再生するために意図されている CDC GDI コマンドのシーケンスのオブジェクトします。 出力を作成します。 GDI コマンドのみ`MoveTo`と`LineTo`、使用することができます。  
  
 メタファイルに必要なコマンドを送信した後、`Close`メタファイルのハンドルを返しますメタファイル デバイス コンテキストを閉じ、メンバー関数。 破棄、`CMetaFileDC`オブジェクト。  
  
 [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile)メタファイルを繰り返し再生するメタファイルのハンドルを使用し、ことができます。 メタファイルできますなど Windows の関数で操作することも[CopyMetaFile](/windows/desktop/api/wingdi/nf-wingdi-copymetafilea)メタファイルをディスクにコピーします。  
  
 メタファイルを不要になったときにメモリから削除、 [DeleteMetaFile](/windows/desktop/api/wingdi/nf-wingdi-deletemetafile) Windows 関数。  
  
 実装することも、`CMetaFileDC`オブジェクトを処理できるようにの呼び出しの出力し、GDI 呼び出しの属性両方`GetTextExtent`します。 このようなメタファイルはより柔軟なと詳細は簡単に再利用できる一般的な GDI コードでは、多くの場合、出力と属性の呼び出しの組み合わせで構成されます。 `CMetaFileDC`クラスは、2 つのデバイス コンテキストを継承`m_hDC`と`m_hAttribDC`、CDC から。 `m_hDC`のすべてのデバイス コンテキストが処理[CDC](../../mfc/reference/cdc-class.md) GDI 呼び出しの出力と`m_hAttribDC`デバイス コンテキストは、CDC GDI 属性のすべての呼び出しを処理します。 通常、これらの 2 つのデバイス コンテキストでは、同じデバイスを参照してください。 場合`CMetaFileDC`DC の属性は、既定で NULL に設定されます。  
  
 画面、プリンター、または、メタファイル以外のデバイスへのポインターを呼び出している 2 つ目のデバイス コンテキストを作成、`SetAttribDC`メンバー関数を使用して、新しいデバイス コンテキストを関連付ける`m_hAttribDC`します。 GDI 呼び出し情報のようになりましたが表示されます、新しい`m_hAttribDC`します。 移動する 出力 GDI 呼び出し`m_hDC`メタファイルを表します。  
  
 詳細については`CMetaFileDC`を参照してください[デバイス コンテキスト](../../mfc/device-contexts.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CMetaFileDC`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
##  <a name="close"></a>  CMetaFileDC::Close  
 メタファイル デバイス コンテキストを閉じて、メタファイルを使用して、再生に使用できる Windows メタファイルのハンドルを作成、 [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile)メンバー関数。  
  
```  
HMETAFILE Close();
```  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合に、有効な HMETAFILEそれ以外の場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 Windows メタファイルのハンドルがなど Windows の関数とメタファイルを操作することもでき[CopyMetaFile](/windows/desktop/api/wingdi/nf-wingdi-copymetafilea)します。  
  
 使用後に、Windows を呼び出すことによって、メタファイルを削除[DeleteMetaFile](/windows/desktop/api/wingdi/nf-wingdi-deletemetafile)関数。  
  
##  <a name="closeenhanced"></a>  CMetaFileDC::CloseEnhanced  
 拡張メタファイル デバイス コンテキストを閉じ、拡張形式、メタファイルを識別するハンドルを返します。  
  
```  
HENHMETAFILE CloseEnhanced();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、拡張メタファイルのハンドルそれ以外の場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 アプリケーションは、この関数によって返される拡張メタファイルのハンドルを使用して、次のタスクを実行できます。  
  
-   拡張メタファイルに格納されている画像を表示します。  
  
-   拡張メタファイルのコピーを作成します。  
  
-   列挙、編集、または拡張メタファイル内の個々 のレコードのコピー  
  
-   拡張メタファイル ヘッダーからメタファイルの内容の説明 (オプション) を取得します。  
  
-   拡張メタファイル ヘッダーのコピーを取得します。  
  
-   拡張メタファイルのバイナリのコピーを取得します。  
  
-   省略可能なパレットで色を列挙します。  
  
-   Windows メタファイルを拡張形式、メタファイルに変換します。  
  
 Win32 を呼び出すことによって、ハンドルを解除する必要が、アプリケーションで拡張メタファイルのハンドルが不要になった場合は、`DeleteEnhMetaFile`関数。  
  
##  <a name="cmetafiledc"></a>  CMetaFileDC::CMetaFileDC  
 構築、 `CMetaFileDC` 2 つのステップ内のオブジェクト。  
  
```  
CMetaFileDC();
```  
  
### <a name="remarks"></a>Remarks  
 最初に、呼び出す`CMetaFileDC`、呼び出して`Create`、Windows メタファイル デバイス コンテキストを作成しにアタッチする`CMetaFileDC`オブジェクト。  
  
##  <a name="create"></a>  CMetaFileDC::Create  
 構築、 `CMetaFileDC` 2 つのステップ内のオブジェクト。  
  
```  
BOOL Create(LPCTSTR lpszFilename = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *場合*  
 Null で終わる文字列へのポインター。 作成するメタファイルのファイル名を指定します。 場合*場合*が null の場合、新しいメモリ内のメタファイルを作成します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 最初に、コンス トラクターを呼び出す`CMetaFileDC`、呼び出して`Create`、Windows メタファイル デバイス コンテキストを作成しにアタッチする`CMetaFileDC`オブジェクト。  
  
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
 *pDCRef*  
 拡張メタファイルの参照のデバイスを識別します。  
  
 *場合*  
 Null で終わる文字列へのポインター。 作成する拡張メタファイルのファイル名を指定します。 メモリ ベースとその内容をオブジェクトが破棄されるとき、または紛失拡張メタファイルは、このパラメーターが NULL の場合、Win32`DeleteEnhMetaFile`関数が呼び出されます。  
  
 *lpBounds*  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)データ構造体または[CRect](../../atl-mfc-shared/reference/crect-class.md) HIMETRIC 単位 (.01 ミリメートル単位)、図の拡張メタファイルに格納されるディメンションを指定するオブジェクト。  
  
 *lpszDescription*  
 画像のタイトルと同様に、画像を作成したアプリケーションの名前を指定する 0 で終わる文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、拡張メタファイル デバイス コンテキストのハンドルそれ以外の場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 この DC は、デバイスに依存しない画像を格納できます。  
  
 Windows で識別される参照のデバイスを使用して、 *pDCRef*解像度と図の最初の表示をデバイス単位を記録するパラメーター。 場合、 *pDCRef*パラメーターが NULL で、現在のディスプレイ デバイスを使用して参照します。  
  
 左と上のメンバー、`RECT`によって示されるデータ構造、 *lpBounds*パラメーター未満でなければなりません右側と下部にあるメンバーをそれぞれします。 図では、四角形の辺に沿ったポイントが含まれます。 場合*lpBounds*が null の場合、グラフィックス デバイス インターフェイス (GDI) は、アプリケーションで描画される画像を囲む最小の四角形の大きさを計算します。 *LpBounds*可能であれば、パラメーターを指定する必要があります。  
  
 指し示さ、文字列、 *lpszDescription*パラメーターは、アプリケーション名と画像名の間の null 文字を含める必要があり、2 つの null 文字で終了する必要があります: たとえば、"XYZ グラフィックス Editor\0Bald Eagle\0\0、"\0 は null 文字を表します。 場合*lpszDescription*が null の場合、拡張メタファイル ヘッダーに対応するエントリはありません。  
  
 アプリケーションでは、この関数によって作成されたドメイン コント ローラーを使用して拡張メタファイルにグラフィックス画像を保存します。 このドメイン コント ローラーを識別するハンドルは、任意の GDI 関数に渡すことができます。  
  
 アプリケーションは、拡張メタファイルに画像を保存した後、画像を表示できる任意の出力デバイスで呼び出すことによって、`CDC::PlayMetaFile`関数。 Windows が指す長方形を使用して、画像を表示するときに、 *lpBounds*パラメーターと位置し、スケールの図を参照するデバイスからの解像度のデータ。 この関数によって返されるデバイス コンテキストには、任意の新しい DC に関連付けられている同じ既定の属性が含まれています。  
  
 アプリケーションは、Win32 を使用する必要があります`GetWinMetaFileBits`拡張メタファイルを以前の Windows メタファイル形式に変換する関数。  
  
 拡張メタファイルのファイル名を使用する必要があります、します。EMF 拡張機能。  
  
## <a name="see-also"></a>関連項目  
 [CDC クラス](../../mfc/reference/cdc-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



