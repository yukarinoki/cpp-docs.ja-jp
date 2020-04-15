---
title: CDumpContext クラス
ms.date: 11/04/2016
f1_keywords:
- CDumpContext
- AFX/CDumpContext
- AFX/CDumpContext::CDumpContext
- AFX/CDumpContext::DumpAsHex
- AFX/CDumpContext::Flush
- AFX/CDumpContext::GetDepth
- AFX/CDumpContext::HexDump
- AFX/CDumpContext::SetDepth
helpviewer_keywords:
- CDumpContext [MFC], CDumpContext
- CDumpContext [MFC], DumpAsHex
- CDumpContext [MFC], Flush
- CDumpContext [MFC], GetDepth
- CDumpContext [MFC], HexDump
- CDumpContext [MFC], SetDepth
ms.assetid: 98c52b2d-14b5-48ed-b423-479a4d1c60fa
ms.openlocfilehash: aa549e5347bf2bd357fa3c28e81a0309ea4f4aff
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374006"
---
# <a name="cdumpcontext-class"></a>CDumpContext クラス

人が読み取ることができる形式でテキストを出力するために、ストリームに依存した診断出力をサポートします。

## <a name="syntax"></a>構文

```
class CDumpContext
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コンテキストを指定します。](#cdumpcontext)|`CDumpContext` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コンテキスト::D](#dumpashex)|指定された項目を 16 進形式でダンプします。|
|[コンテキスト::フラッシュ](#flush)|ダンプ コンテキスト バッファー内のデータをフラッシュします。|
|[コンテキストを取得します。](#getdepth)|ダンプの深さに対応する整数を取得します。|
|[コンテキスト::ヘックスダンプ](#hexdump)|配列に含まれるバイトを 16 進形式でダンプします。|
|[コンテキスト::セットデプス](#setdepth)|ダンプの深さを設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[コンテキスト::演算子&lt;&lt;](#operator_lt_lt)|変数とオブジェクトをダンプ コンテキストに挿入します。|

## <a name="remarks"></a>解説

`CDumpContext`は基本クラスを持っていません。

ダンプの大部分では、宣言済`CDumpContext`みのオブジェクトである[afxDump](diagnostic-services.md#afxdump)を使用できます。 この`afxDump`オブジェクトは、デバッグ バージョンの Microsoft Foundation クラス ライブラリでのみ使用できます。

メモリ[診断サービス](../../mfc/reference/diagnostic-services.md)の中には、`afxDump`その出力に使用するいくつかのサービスがあります。

Windows 環境では、定義済`afxDump`みのオブジェクトからの出力は、概念的には`cerr`ストリームに似ていて、Windows 関数`OutputDebugString`を介してデバッガにルーティングされます。

このクラスには、オブジェクトのデータを**<<** ダンプするポインター`CObject`に対して、オーバーロードされた挿入 ( ) 演算子があります。 `CDumpContext` 派生オブジェクトのカスタム ダンプ形式が必要な場合は[、CObject::Dump](../../mfc/reference/cobject-class.md#dump)をオーバーライドします。 ほとんどの Microsoft Foundation クラスは`Dump`、オーバーライドされたメンバー関数を実装します。

など`CObject``CString`から派生していないクラスには、 `CTime`、 など`CTimeSpan`、頻繁に使用される構造体`CDumpContext``CFileStatus``CPoint`と同様に、独自のオーバーロードされた挿入演算子があります。 `CRect`

クラスの実装で[IMPLEMENT_DYNAMIC](../../mfc/reference/run-time-object-model-services.md#implement_dynamic)または[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)マクロを使用する`CObject::Dump`場合は、派生クラスの名前を出力します。 `CObject` それ以外の場合は`CObject`、 が印刷されます。

この`CDumpContext`クラスは、ライブラリのデバッグ バージョンとリリース バージョンの両方で使用`Dump`できますが、メンバー関数はデバッグ バージョンでのみ定義されます。 **#ifdef_DEBUG** / `#endif`ステートメントを使用して、カスタム`Dump`メンバー関数を含む診断コードを囲みます。

独自`CDumpContext`のオブジェクトを作成する前に`CFile`、ダンプ先として機能するオブジェクトを作成する必要があります。

の詳細については、「 `CDumpContext` [MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)」を参照してください。

**#define _DEBUG**

## <a name="inheritance-hierarchy"></a>継承階層

`CDumpContext`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="cdumpcontextcdumpcontext"></a><a name="cdumpcontext"></a>コンテキストを指定します。

クラス`CDumpContext`のオブジェクトを構築します。

```
CDumpContext(CFile* pFile = NULL);
```

### <a name="parameters"></a>パラメーター

*ファイル*<br/>
ダンプ先である`CFile`オブジェクトへのポインター。

### <a name="remarks"></a>解説

オブジェクト`afxDump`は自動的に構築されます。

ダンプ コンテキストがアクティブな`CFile`間は、基になるコンテキストに書き込まないでください。そうしないと、ダンプに干渉します。 Windows 環境では、出力は Windows 関数`OutputDebugString`を介してデバッガーにルーティングされます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#12](../../mfc/codesnippet/cpp/cdumpcontext-class_1.cpp)]

## <a name="cdumpcontextdumpashex"></a><a name="dumpashex"></a>コンテキスト::D

指定した型を 16 進数でダンプします。

```
CDumpContext& DumpAsHex(BYTE b);
CDumpContext& DumpAsHex(DWORD dw);
CDumpContext& DumpAsHex(int n);
CDumpContext& DumpAsHex(LONG l);
CDumpContext& DumpAsHex(LONGLONG n);
CDumpContext& DumpAsHex(UINT u);
CDumpContext& DumpAsHex(ULONGLONG n);
CDumpContext& DumpAsHex(WORD w);
```

### <a name="return-value"></a>戻り値

`CDumpContext` オブジェクトへの参照です。

### <a name="remarks"></a>解説

指定した型の項目を 16 進数としてダンプします。 配列をダンプするには[、CDumpContext::HexDump](#hexdump)を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#13](../../mfc/codesnippet/cpp/cdumpcontext-class_2.cpp)]

## <a name="cdumpcontextflush"></a><a name="flush"></a>コンテキスト::フラッシュ

バッファーに残っているデータをダンプ コンテキストに添付されたファイルに強制的に書き込みます。

```
void Flush();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#14](../../mfc/codesnippet/cpp/cdumpcontext-class_3.cpp)]

## <a name="cdumpcontextgetdepth"></a><a name="getdepth"></a>コンテキストを取得します。

深いダンプと浅いダンプのどちらが処理中であるかを判断します。

```
int GetDepth() const;
```

### <a name="return-value"></a>戻り値

によって設定された`SetDepth`ダンプの深さ。

### <a name="example"></a>例

  [「詳細](#setdepth)」の例を参照してください。

## <a name="cdumpcontexthexdump"></a><a name="hexdump"></a>コンテキスト::ヘックスダンプ

16 進数としてフォーマットされたバイト配列をダンプします。

```
void HexDump(
    LPCTSTR lpszLine,
    BYTE* pby,
    int nBytes,
    int nWidth);
```

### <a name="parameters"></a>パラメーター

*lpszLine*<br/>
新しい行の先頭に出力する文字列。

*pby*<br/>
ダンプするバイトを含むバッファーへのポインター。

*Nbytes*<br/>
ダンプするバイト数。

*n幅*<br/>
1 行にダンプされる最大バイト数 (出力行の幅ではありません)。

### <a name="remarks"></a>解説

16 進数として特定の単一の項目の種類をダンプするには[、CDumpContext::DumpAsHex](#dumpashex)を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#15](../../mfc/codesnippet/cpp/cdumpcontext-class_4.cpp)]

## <a name="cdumpcontextoperator-ltlt"></a><a name="operator_lt_lt"></a>コンテキスト::演算子&lt;&lt;

指定したデータをダンプ コンテキストに出力します。

```
CDumpContext& operator<<(const CObject* pOb);
CDumpContext& operator<<(const CObject& ob);
CDumpContext& operator<<(LPCTSTR lpsz);
CDumpContext& operator<<(const void* lp);
CDumpContext& operator<<(BYTE by);
CDumpContext& operator<<(WORD w);
CDumpContext& operator<<(DWORD dw);
CDumpContext& operator<<(int n);
CDumpContext& operator<<(double d);
CDumpContext& operator<<(float f);
CDumpContext& operator<<(LONG l);
CDumpContext& operator<<(UINT u);
CDumpContext& operator<<(LPCWSTR lpsz);
CDumpContext& operator<<(LPCSTR lpsz);
CDumpContext& operator<<(LONGLONG n);
CDumpContext& operator<<(ULONGLONG n);
CDumpContext& operator<<(HWND h);
CDumpContext& operator<<(HDC h);
CDumpContext& operator<<(HMENU h);
CDumpContext& operator<<(HACCEL h);
CDumpContext& operator<<(HFONT h);
```

### <a name="return-value"></a>戻り値

`CDumpContext` 参照。 戻り値を使用すると、ソース コードの 1 行に複数の挿入を記述できます。

### <a name="remarks"></a>解説

挿入演算子は、ポインターとほとんどの`CObject`プリミティブ型に対してオーバーロードされます。 文字へのポインターは、文字列の内容のダンプになります。**void**へのポインタは、アドレスの 16 進ダンプのみになります。 LONGLONG を指定すると、64 ビット符号付き整数がダンプされます。ULONG は、64 ビット符号なし整数のダンプになります。

クラスの実装で IMPLEMENT_DYNAMIC またはIMPLEMENT_SERIAL マクロを使用する場合、挿入演算子は、`CObject::Dump`を通じて派生クラスの名前`CObject`を出力します。 それ以外の場合は`CObject`、 が印刷されます。 クラスの関数を`Dump`オーバーライドする場合は、16 進ダンプではなく、オブジェクトの内容をより意味のある出力で出力できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#17](../../mfc/codesnippet/cpp/cdumpcontext-class_5.cpp)]

## <a name="cdumpcontextsetdepth"></a><a name="setdepth"></a>コンテキスト::セットデプス

ダンプの深さを設定します。

```
void SetDepth(int nNewDepth);
```

### <a name="parameters"></a>パラメーター

*新しい深さ*<br/>
新しい深さの値。

### <a name="remarks"></a>解説

他のオブジェクトへのポインターを含たないプリミティブ型`CObject`または単純な型をダンプする場合は、値 0 で十分です。 0 より大きい値は、すべてのオブジェクトが再帰的にダンプされる深いダンプを指定します。 たとえば、コレクションの詳細なダンプでは、コレクションのすべての要素がダンプされます。 派生クラスでは、他の特定の深度値を使用できます。

> [!NOTE]
> 循環参照は深いダンプでは検出されず、無限ループが発生する可能性があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#16](../../mfc/codesnippet/cpp/cdumpcontext-class_6.cpp)]

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CFile クラス](../../mfc/reference/cfile-class.md)<br/>
[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)
