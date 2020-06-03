---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CMetaFileDC
- AFXEXT/CMetaFileDC
- AFXEXT/CMetaFileDC::CMetaFileDC
- AFXEXT/CMetaFileDC::Close
- AFXEXT/CMetaFileDC::CloseEnhanced
- AFXEXT/CMetaFileDC::Create
- AFXEXT/CMetaFileDC::CreateEnhanced
helpviewer_keywords:
- CMetaFileDC [MFC], CMetaFileDC
- CMetaFileDC [MFC], Close
- CMetaFileDC [MFC], CloseEnhanced
- CMetaFileDC [MFC], Create
- CMetaFileDC [MFC], CreateEnhanced
ms.assetid: ffce60fa-4181-4d46-9832-25e46fad4db4
ms.openlocfilehash: 0919dacfd758df39064c5381690e9e23a029fcd1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369951"
---
# <a name="cmetafiledc-class"></a>クラス

イメージやテキストを自由に作成するための一連のグラフィック デバイス インターフェイス (GDI) コマンドを含む Windows のメタファイルを実装します。

## <a name="syntax"></a>構文

```
class CMetaFileDC : public CDC
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CメタファイルDC:CメタファイルDC](#cmetafiledc)|`CMetaFileDC` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ファイルDC::閉じる](#close)|デバイス コンテキストを閉じ、メタファイル ハンドルを作成します。|
|[ファイル DC::クローズ拡張](#closeenhanced)|拡張メタファイル デバイス コンテキストを閉じ、拡張メタファイル ハンドルを作成します。|
|[ファイルDC:作成](#create)|Windows メタファイル デバイス コンテキストを作成し、オブジェクト`CMetaFileDC`にアタッチします。|
|[CMetaFileDC::拡張の作成](#createenhanced)|拡張形式のメタファイルのメタファイル デバイス コンテキストを作成します。|

## <a name="remarks"></a>解説

Windows メタファイルを実装するには、まずオブジェクト`CMetaFileDC`を作成します。 コンストラクターを`CMetaFileDC`呼び出し[、Create](#create)メンバー関数を`CMetaFileDC`呼び出します。

次に、`CMetaFileDC`再生する CDC GDI コマンドのシーケンスをオブジェクトに送信します。 や などの`MoveTo``LineTo`出力を作成する GDI コマンドのみを使用できます。

メタファイルに目的のコマンドを送信した後、メンバー関数を`Close`呼び出します。 次に、オブジェクト`CMetaFileDC`を破棄します。

[CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile)はメタファイル ハンドルを使用してメタファイルを繰り返し再生できます。 メタファイルは、メタファイルをディスクにコピーする[CopyMetaFile](/windows/win32/api/wingdi/nf-wingdi-copymetafilew)などの Windows 関数によっても操作できます。

メタファイルが不要になったら、そのメタファイルを削除して、Windows の機能を使用してメモリから[削除](/windows/win32/api/wingdi/nf-wingdi-deletemetafile)します。

また、`CMetaFileDC`出力呼び出しと、 などの`GetTextExtent`属性 GDI 呼び出しの両方を処理できるように、オブジェクトを実装することもできます。 このようなメタファイルはより柔軟で、出力と属性の呼び出しが混在する一般的な GDI コードをより簡単に再利用できます。 この`CMetaFileDC`クラスは、CDC`m_hDC`から 2`m_hAttribDC`つのデバイス コンテキストと を継承します。 デバイス`m_hDC`コンテキストは、すべての[CDC](../../mfc/reference/cdc-class.md) GDI`m_hAttribDC`出力呼び出しを処理し、デバイス コンテキストは、すべての CDC GDI 属性呼び出しを処理します。 通常、これら 2 つのデバイス コンテキストは同じデバイスを参照します。 の場合`CMetaFileDC`、属性 DC は既定で NULL に設定されます。

画面、プリンター、またはメタファイル以外のデバイスを指す 2 つ目のデバイス コンテキストを作成し`SetAttribDC`、メンバー関数を呼び出して新`m_hAttribDC`しいデバイス コンテキストを に関連付けます。 GDI から情報を求める情報が新しい`m_hAttribDC`. 出力 GDI 呼び`m_hDC`出しは、メタファイルを表す に行きます。

の詳細については、「 `CMetaFileDC`[デバイス コンテキスト](../../mfc/device-contexts.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CMetaFileDC`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxext.h

## <a name="cmetafiledcclose"></a><a name="close"></a>ファイルDC::閉じる

メタファイル デバイス コンテキストを閉じ[、CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile)メンバー関数を使用してメタファイルを再生するために使用できる Windows メタファイル ハンドルを作成します。

```
HMETAFILE Close();
```

### <a name="return-value"></a>戻り値

関数が正常に実行された場合は有効な HMETAFILE。それ以外の場合は NULL。

### <a name="remarks"></a>解説

Windows メタファイル ハンドルを使用して、[コピーメタ](/windows/win32/api/wingdi/nf-wingdi-copymetafilew)ファイルなどの Windows 関数を使用してメタファイルを操作することもできます。

使用後に、Windows の削除メタファイル関数を呼び出して[メタファイルを削除](/windows/win32/api/wingdi/nf-wingdi-deletemetafile)します。

## <a name="cmetafiledccloseenhanced"></a><a name="closeenhanced"></a>ファイル DC::クローズ拡張

拡張メタファイル デバイス コンテキストを閉じ、拡張形式のメタファイルを識別するハンドルを返します。

```
HENHMETAFILE CloseEnhanced();
```

### <a name="return-value"></a>戻り値

正常終了した場合は、拡張メタファイルのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

アプリケーションは、この関数によって返される拡張メタファイル ハンドルを使用して、次のタスクを実行できます。

- 拡張メタファイルに保存されている画像を表示する

- 拡張メタファイルのコピーを作成する

- 拡張メタファイル内の個々のレコードを列挙、編集、またはコピーする

- 拡張メタファイル ヘッダーからメタファイルの内容の説明を取得するオプション

- 拡張メタファイル ヘッダーのコピーを取得する

- 拡張メタファイルのバイナリ コピーを取得する

- オプションのパレットで色を列挙する

- 拡張形式のメタファイルを Windows 形式のメタファイルに変換する

アプリケーションが拡張メタファイル ハンドルを必要としなくなった場合は、Win32`DeleteEnhMetaFile`関数を呼び出してハンドルを解放する必要があります。

## <a name="cmetafiledccmetafiledc"></a><a name="cmetafiledc"></a>CメタファイルDC:CメタファイルDC

2`CMetaFileDC`つの手順でオブジェクトを作成します。

```
CMetaFileDC();
```

### <a name="remarks"></a>解説

まず、`CMetaFileDC`を呼び`Create`出し、次に Windows メタファイル デバイス コンテキストを`CMetaFileDC`作成し、オブジェクトにアタッチする を呼び出します。

## <a name="cmetafiledccreate"></a><a name="create"></a>ファイルDC:作成

2`CMetaFileDC`つの手順でオブジェクトを作成します。

```
BOOL Create(LPCTSTR lpszFilename = NULL);
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
NULL で終わる文字列を指します。 作成するメタファイルのファイル名を指定します。 *lpszFilename*が NULL の場合、新しいインメモリ メタファイルが作成されます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

まず、コンストラクタ`CMetaFileDC`を呼び出してから`Create`、Windows メタファイル デバイス コンテキストを作成して`CMetaFileDC`オブジェクトにアタッチする を呼び出します。

## <a name="cmetafiledccreateenhanced"></a><a name="createenhanced"></a>CMetaFileDC::拡張の作成

拡張形式メタファイルのデバイス コンテキストを作成します。

```
BOOL CreateEnhanced(
    CDC* pDCRef,
    LPCTSTR lpszFileName,
    LPCRECT lpBounds,
    LPCTSTR lpszDescription);
```

### <a name="parameters"></a>パラメーター

*を参照します。*<br/>
拡張メタファイルの参照デバイスを識別します。

*ファイル名*<br/>
NULL で終わる文字列を指します。 作成する拡張メタファイルのファイル名を指定します。 このパラメーターが NULL の場合、拡張メタファイルはメモリ ベースであり、オブジェクトが破棄されたとき、または Win32`DeleteEnhMetaFile`関数が呼び出されたときにその内容が失われます。

*lpBounds*<br/>
拡張メタファイルに格納される画像の寸法を HIMETRIC 単位 (0.01 ミリ単位) 単位で指定する[RECT](/windows/win32/api/windef/ns-windef-rect)データ構造体または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトへのポイント。

*説明をします。*<br/>
画像を作成したアプリケーションの名前と、画像のタイトルを指定する、ゼロで終わる文字列を指します。

### <a name="return-value"></a>戻り値

正常終了した場合は、拡張メタファイルのデバイス コンテキストのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

この DC は、デバイスに依存しない画像を格納するために使用できます。

Windows は *、pDCRef*パラメーターで識別される参照デバイスを使用して、画像が最初に表示されたデバイスの解像度と単位を記録します。 *pDCRef*パラメーターが NULL の場合、参照用に現在の表示装置が使用されます。

*lpBounds*パラメーターによって指定`RECT`されるデータ構造体の左と上のメンバーは、それぞれ右と下のメンバーよりも小さくする必要があります。 四角形の端に沿ったポイントが画像に含まれます。 *lpBounds*が NULL の場合、グラフィックス デバイス インターフェイス (GDI) は、アプリケーションによって描画された画像を囲むことができる最小の四角形のサイズを計算します。 可能な場合は *、lpBounds*パラメーターを指定する必要があります。

*lpszDescription*パラメータで指定される文字列には、アプリケーション名と画像名の間に null 文字が含まれ、2 つの NULL 文字で終わる必要があります。 *lpszDescription*が NULL の場合、拡張メタファイル ヘッダーに対応するエントリはありません。

アプリケーションは、この関数によって作成された DC を使用して、グラフィックス画像を拡張メタファイルに格納します。 この DC を識別するハンドルは、任意の GDI 関数に渡すことができます。

アプリケーションは、拡張メタファイルに画像を格納した後、関数を呼び出すことによって、任意の出力デバイス`CDC::PlayMetaFile`上に画像を表示できます。 ピクチャを表示する場合、Windows は *、lpBounds*パラメーターで示された四角形と、参照デバイスからの解像度データを使用して、画像を配置およびスケーリングします。 この関数によって返されるデバイス コンテキストには、新しい DC に関連付けられた同じ既定の属性が含まれています。

アプリケーションは、拡張メタファイルを`GetWinMetaFileBits`古い Windows メタファイル形式に変換するために Win32 関数を使用する必要があります。

拡張メタファイルのファイル名には.EMF 拡張。

## <a name="see-also"></a>関連項目

[CDCクラス](../../mfc/reference/cdc-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
