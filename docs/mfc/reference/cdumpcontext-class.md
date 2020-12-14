---
description: '詳細情報: CDumpContext クラス'
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
ms.openlocfilehash: 955be92c4a3b08fe6e1d5a947166133143667ac7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184777"
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
|[CDumpContext:: CDumpContext](#cdumpcontext)|`CDumpContext` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDumpContext::D umpAsHex](#dumpashex)|指定された項目を16進形式でダンプします。|
|[CDumpContext:: Flush](#flush)|ダンプコンテキストバッファー内のすべてのデータをフラッシュします。|
|[CDumpContext:: GetDepth](#getdepth)|ダンプの深さに対応する整数を取得します。|
|[CDumpContext:: HexDump](#hexdump)|配列に格納されているバイトを16進形式でダンプします。|
|[CDumpContext:: SetDepth](#setdepth)|ダンプの深さを設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CDumpContext:: operator &lt;&lt;](#operator_lt_lt)|変数とオブジェクトをダンプコンテキストに挿入します。|

## <a name="remarks"></a>解説

`CDumpContext` に基底クラスがありません。

ダンプの大部分には、事前オブジェクトである [afxDump](diagnostic-services.md#afxdump)を使用でき `CDumpContext` ます。 `afxDump`オブジェクトは、Microsoft Foundation Class ライブラリのデバッグバージョンでのみ使用できます。

いくつかのメモリ [診断サービス](../../mfc/reference/diagnostic-services.md) が `afxDump` 出力に使用します。

Windows 環境では、定義済みのオブジェクトからの出力は、 `afxDump` 概念的にはストリームに似て `cerr` いますが、windows の関数を使用してデバッガーにルーティングされ `OutputDebugString` ます。

`CDumpContext`クラスには、 **<<** `CObject` オブジェクトのデータをダンプするポインターのオーバーロードされた挿入 () 演算子があります。 派生オブジェクトにカスタムダンプ形式が必要な場合は、 [CObject::D ump](../../mfc/reference/cobject-class.md#dump)をオーバーライドします。 ほとんどの Microsoft Foundation クラスは、オーバーライドさ `Dump` れたメンバー関数を実装します。

、、など、から派生していないクラスには、、、などの `CObject` `CString` 頻繁に `CTime` `CTimeSpan` `CDumpContext` 使用される構造と同様に、独自のオーバーロードされた挿入演算子があり `CFileStatus` `CPoint` `CRect` ます。

クラスの実装で [IMPLEMENT_DYNAMIC](../../mfc/reference/run-time-object-model-services.md#implement_dynamic) または [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) マクロを使用すると、は、 `CObject::Dump` 派生クラスの名前を出力し `CObject` ます。 それ以外の場合は印刷され `CObject` ます。

クラスは、 `CDumpContext` ライブラリのデバッグバージョンとリリースバージョンの両方で使用できますが、 `Dump` メンバー関数はデバッグバージョンでのみ定義されています。 **#Ifdef _DEBUG** ステートメントを使用して  /  `#endif` 、カスタムメンバー関数を含む診断コードをかっこで囲み `Dump` ます。

独自のオブジェクトを作成する前に `CDumpContext` 、 `CFile` ダンプ先として機能するオブジェクトを作成する必要があります。

の詳細につい `CDumpContext` ては、「 [MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)」を参照してください。

**#define _DEBUG**

## <a name="inheritance-hierarchy"></a>継承階層

`CDumpContext`

## <a name="requirements"></a>要件

**ヘッダー:** afx

## <a name="cdumpcontextcdumpcontext"></a><a name="cdumpcontext"></a> CDumpContext:: CDumpContext

クラスのオブジェクトを構築 `CDumpContext` します。

```
CDumpContext(CFile* pFile = NULL);
```

### <a name="parameters"></a>パラメーター

*pFile*<br/>
`CFile`ダンプ先のオブジェクトへのポインター。

### <a name="remarks"></a>解説

`afxDump`オブジェクトは自動的に構築されます。

ダンプコンテキストがアクティブになっている間は、基になるに書き込みません `CFile` 。それ以外の場合は、ダンプの影響を受けることになります。 Windows 環境では、出力は Windows の関数を介してデバッガーにルーティングされ `OutputDebugString` ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#12](../../mfc/codesnippet/cpp/cdumpcontext-class_1.cpp)]

## <a name="cdumpcontextdumpashex"></a><a name="dumpashex"></a> CDumpContext::D umpAsHex

指定された型を16進数値としてダンプします。

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

このメンバー関数を呼び出して、指定した型の項目を16進数値としてダンプします。 配列をダンプするには、 [CDumpContext:: HexDump](#hexdump)を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#13](../../mfc/codesnippet/cpp/cdumpcontext-class_2.cpp)]

## <a name="cdumpcontextflush"></a><a name="flush"></a> CDumpContext:: Flush

バッファー内の残りのデータを、ダンプコンテキストにアタッチされたファイルに強制的に書き込むようにします。

```cpp
void Flush();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#14](../../mfc/codesnippet/cpp/cdumpcontext-class_3.cpp)]

## <a name="cdumpcontextgetdepth"></a><a name="getdepth"></a> CDumpContext:: GetDepth

Deep または浅いダンプが処理中かどうかを判断します。

```
int GetDepth() const;
```

### <a name="return-value"></a>戻り値

によって設定されたダンプの深さ `SetDepth` 。

### <a name="example"></a>例

  [Setdepth](#setdepth)の例を参照してください。

## <a name="cdumpcontexthexdump"></a><a name="hexdump"></a> CDumpContext:: HexDump

16進数値として書式設定されたバイトの配列をダンプします。

```cpp
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
ダンプするバイトを格納しているバッファーへのポインター。

*nBytes*<br/>
ダンプするバイト数。

*nWidth*<br/>
行ごとにダンプされる最大バイト数 (出力行の幅ではありません)。

### <a name="remarks"></a>解説

1つの特定の項目の種類を16進数としてダンプするには、 [CDumpContext::D umpashex](#dumpashex)を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#15](../../mfc/codesnippet/cpp/cdumpcontext-class_4.cpp)]

## <a name="cdumpcontextoperator-ltlt"></a><a name="operator_lt_lt"></a> CDumpContext:: operator &lt;&lt;

指定されたデータをダンプコンテキストに出力します。

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

`CDumpContext` 参照。 戻り値を使用すると、1行のソースコードに複数の挿入を書き込むことができます。

### <a name="remarks"></a>解説

挿入演算子は、 `CObject` ポインターやほとんどのプリミティブ型に対してオーバーロードされます。 文字へのポインターは、文字列の内容のダンプを生成します。へのポインターは、 **`void`** アドレスの16進数のダンプだけを生成します。 LONGLONG では、64ビット符号付き整数のダンプが生成されます。ULONGLONG は、64ビット符号なし整数のダンプを生成します。

クラスの実装で IMPLEMENT_DYNAMIC または IMPLEMENT_SERIAL マクロを使用する場合、挿入演算子によって、から `CObject::Dump` 派生したクラスの名前が出力され `CObject` ます。 それ以外の場合は印刷され `CObject` ます。 クラスの関数をオーバーライドすると `Dump` 、16進数のダンプではなく、オブジェクトの内容に対してより意味のある出力を提供できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#17](../../mfc/codesnippet/cpp/cdumpcontext-class_5.cpp)]

## <a name="cdumpcontextsetdepth"></a><a name="setdepth"></a> CDumpContext:: SetDepth

ダンプの深さを設定します。

```cpp
void SetDepth(int nNewDepth);
```

### <a name="parameters"></a>パラメーター

*nNewDepth*<br/>
新しい深さの値。

### <a name="remarks"></a>解説

プリミティブ型をダンプする場合、または `CObject` 他のオブジェクトへのポインターが含まれていない単純な場合は、値を0にするだけで十分です。 0より大きい値は、すべてのオブジェクトが再帰的にダンプされる詳細ダンプを指定します。 たとえば、コレクションの詳細ダンプによって、コレクションのすべての要素がダンプされます。 派生クラスでは、他の特定の深さの値を使用できます。

> [!NOTE]
> 詳細ダンプで循環参照が検出されないため、無限ループが発生する可能性があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#16](../../mfc/codesnippet/cpp/cdumpcontext-class_6.cpp)]

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CFile クラス](../../mfc/reference/cfile-class.md)<br/>
[CObject クラス](../../mfc/reference/cobject-class.md)
