---
title: CDumpContext クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDumpContext
- AFX/CDumpContext
- AFX/CDumpContext::CDumpContext
- AFX/CDumpContext::DumpAsHex
- AFX/CDumpContext::Flush
- AFX/CDumpContext::GetDepth
- AFX/CDumpContext::HexDump
- AFX/CDumpContext::SetDepth
dev_langs:
- C++
helpviewer_keywords:
- CDumpContext [MFC], CDumpContext
- CDumpContext [MFC], DumpAsHex
- CDumpContext [MFC], Flush
- CDumpContext [MFC], GetDepth
- CDumpContext [MFC], HexDump
- CDumpContext [MFC], SetDepth
ms.assetid: 98c52b2d-14b5-48ed-b423-479a4d1c60fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7acd7e94dbb45439a1812f8572ef442e43f9dab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
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
|[CDumpContext::CDumpContext](#cdumpcontext)|`CDumpContext` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDumpContext::DumpAsHex](#dumpashex)|16 進形式で指定されたアイテムをダンプします。|  
|[CDumpContext::Flush](#flush)|ダンプ コンテキスト バッファー内のデータをフラッシュします。|  
|[CDumpContext::GetDepth](#getdepth)|ダンプの深さに対応する整数値を取得します。|  
|[に](#hexdump)|16 進数形式の配列に含まれるバイト数をダンプします。|  
|[CDumpContext::SetDepth](#setdepth)|ダンプの深さを設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CDumpContext::operator &lt;&lt;](#operator_lt_lt)|ダンプ コンテキストには、変数およびオブジェクトを挿入します。|  
  
## <a name="remarks"></a>コメント  
 `CDumpContext` 基本クラスはありません。  
  
 使用することができます[afxDump](diagnostic-services.md#afxdump)は事前に宣言された`CDumpContext`ダンプのほとんどのオブジェクト。 `afxDump`オブジェクトは、Microsoft Foundation Class ライブラリのデバッグ バージョンでのみ使用できます。  
  
 メモリのいくつか[診断サービス](../../mfc/reference/diagnostic-services.md)使用`afxDump`出力にします。  
  
 [Windows 環境]、定義済みの出力で`afxDump`オブジェクト、概念的に似ています、`cerr`ストリーム、Windows の機能を使用して、デバッガーにルーティングされる**OutputDebugString**です。  
  
 `CDumpContext`クラスには、オーバー ロードされた挿入 ( **<<**) 演算子を`CObject`オブジェクトのデータをダンプするポインター。 派生オブジェクトのカスタムのダンプ形式を必要がある場合は、オーバーライド[CObject::Dump](../../mfc/reference/cobject-class.md#dump)です。 ほとんどの Microsoft Foundation classes をオーバーライドされた実装`Dump`メンバー関数。  
  
 クラスから派生していない`CObject`など`CString`、 `CTime`、および`CTimeSpan`、独自のオーバー ロードがある`CDumpContext`などの操作を頻繁に使用される構造体としての挿入演算子**CFileStatus**、 `CPoint`、および`CRect`です。  
  
 使用する場合、 [IMPLEMENT_DYNAMIC](../../mfc/reference/run-time-object-model-services.md#implement_dynamic)または[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)マクロ、クラスの実装で`CObject::Dump`の名前を出力、 `CObject`-クラスを派生します。 それ以外の場合は印刷`CObject`です。  
  
 `CDumpContext`クラスは、ライブラリのデバッグとリリースの両方のバージョンで利用可能ですが、`Dump`メンバー関数は、デバッグ バージョンでのみ定義されています。 使用して **#ifdef _DEBUG**  /  `#endif`ステートメントなど、カスタム、診断コードを角かっこを`Dump`メンバー関数。  
  
 独自に作成する前に`CDumpContext`オブジェクトを作成する必要があります、`CFile`ダンプのエクスポート先として機能するオブジェクト。  
  
 詳細については`CDumpContext`を参照してください[MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)です。  
  
 **#define _DEBUG を define**  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CDumpContext`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="cdumpcontext"></a>  CDumpContext::CDumpContext  
 クラスのオブジェクトを構築`CDumpContext`です。  
  
```  
CDumpContext(CFile* pFile = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFile`  
 ポインター、`CFile`ダンプの転送先となるオブジェクト。  
  
### <a name="remarks"></a>コメント  
 `afxDump`オブジェクトが自動的に構築します。  
  
 基になる書き込みません`CFile`ダンプに干渉するが、ダンプ コンテキストは、アクティブであるそれ以外の場合は、します。 Windows 環境下で、出力は、Windows の機能を使用して、デバッガーにルーティング**OutputDebugString**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#12](../../mfc/codesnippet/cpp/cdumpcontext-class_1.cpp)]  
  
##  <a name="dumpashex"></a>  CDumpContext::DumpAsHex  
 指定した型の 16 進数値として書式設定をダンプします。  
  
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
 `CDumpContext` オブジェクトへの参照。  
  
### <a name="remarks"></a>コメント  
 16 進数として指定した型の項目をダンプする場合は、このメンバー関数を呼び出します。 配列をダンプする[に](#hexdump)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#13](../../mfc/codesnippet/cpp/cdumpcontext-class_2.cpp)]  
  
##  <a name="flush"></a>  CDumpContext::Flush  
 強制的に実行ファイルに書き込まれるバッファーに残っているデータは、ダンプ コンテキストにアタッチします。  
  
```  
void Flush();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#14](../../mfc/codesnippet/cpp/cdumpcontext-class_3.cpp)]  
  
##  <a name="getdepth"></a>  CDumpContext::GetDepth  
 Deep または shallow ダンプが進行中かどうかを判断します。  
  
```  
int GetDepth() const;  
```  
  
### <a name="return-value"></a>戻り値  
 によって設定されたダンプの深さ`SetDepth`です。  
  
### <a name="example"></a>例  
  例を参照して[SetDepth](#setdepth)です。  
  
##  <a name="hexdump"></a>  に  
 16 進数値として書式設定されたバイトの配列をダンプします。  
  
```  
void HexDump(
    LPCTSTR lpszLine,  
    BYTE* pby,  
    int nBytes,  
    int nWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszLine*  
 新しい行の開始時に出力する文字列。  
  
 *pby*  
 ダンプするバイトを格納するバッファーへのポインター。  
  
 `nBytes`  
 ダンプするバイト数。  
  
 `nWidth`  
 1 行 (出力行の幅されません) の最大バイト数にダンプします。  
  
### <a name="remarks"></a>コメント  
 16 進数として、特定の 1 つの項目の種類をダンプを呼び出す[CDumpContext::DumpAsHex](#dumpashex)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#15](../../mfc/codesnippet/cpp/cdumpcontext-class_4.cpp)]  
  
##  <a name="operator_lt_lt"></a>  CDumpContext::operator &lt;&lt;  
 ダンプ コンテキストの指定されたデータを出力します。  
  
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
 A`CDumpContext`参照します。 戻り値を使用するには、ソース コードの 1 行に複数の挿入を記述できます。  
  
### <a name="remarks"></a>コメント  
 に対して、挿入演算子がオーバー ロード`CObject`ほとんどのプリミティブ型の場合と同様のポインター。 文字列の内容のダンプに文字結果へのポインターポインター`void`のみアドレスの 16 進数のダンプの結果します。 A **LONGLONG** 64 ビットの符号付き整数のダンプの結果A**使い**64 ビット符号なし整数のダンプになります。  
  
 使用する場合、`IMPLEMENT_DYNAMIC`または`IMPLEMENT_SERIAL`マクロで、クラス、挿入演算子の実装を通じて`CObject::Dump`の名前を印刷、 `CObject`-派生クラス。 それ以外の場合は印刷`CObject`です。 オーバーライドする場合、`Dump`クラスの関数は、16 進数のダンプの代わりに、オブジェクトの内容のわかりやすい出力を提供できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#17](../../mfc/codesnippet/cpp/cdumpcontext-class_5.cpp)]  
  
##  <a name="setdepth"></a>  CDumpContext::SetDepth  
 ダンプの深さを設定します。  
  
```  
void SetDepth(int nNewDepth);
```  
  
### <a name="parameters"></a>パラメーター  
 *nNewDepth*  
 新しい深さの値。  
  
### <a name="remarks"></a>コメント  
 プリミティブ型または単純なをダンプする場合`CObject`し、その他のオブジェクトへのポインターが含まれていない、0 の値で十分です。 0 = すべてのオブジェクトがある深いダンプよりも大きい値では、再帰的にダンプします。 たとえば、コレクションのディープ ダンプは、コレクションのすべての要素がダンプされます。 派生クラスで他の特定の深さの値を使用することがあります。  
  
> [!NOTE]
>  循環参照は、深いダンプで認識されないされ、無限ループになることができます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#16](../../mfc/codesnippet/cpp/cdumpcontext-class_6.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFile クラス](../../mfc/reference/cfile-class.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)
