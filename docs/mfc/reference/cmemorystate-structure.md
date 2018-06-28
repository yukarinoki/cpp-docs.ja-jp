---
title: 行い構造 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMemoryState
dev_langs:
- C++
helpviewer_keywords:
- CMemoryState structure [MFC]
- memory leaks [MFC], detecting
- detecting memory leaks [MFC]
ms.assetid: 229d9de7-a6f3-4cc6-805b-5a9d9b1bfe1d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba1d156d9453cd6a74a3543295d9d90d761e77f9
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040747"
---
# <a name="cmemorystate-structure"></a>関数の構造体
プログラムでのメモリ リークを検出する便利な手段を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
struct CMemoryState  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMemoryState::CMemoryState](#cmemorystate)|メモリのチェックポイントを制御するクラスのような構造を構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMemoryState::Checkpoint](#checkpoint)|現在のメモリ状態のスナップショット (チェックポイント) を取得します。|  
|[CMemoryState::Difference](#difference)|型の 2 つのオブジェクト間の差を計算`CMemoryState`です。|  
|[Cmemorystate::dumpallobjectssince](#dumpallobjectssince)|以前のチェックポイント以降には、現在割り当てられているすべてのオブジェクトの概要をダンプします。|  
|[CMemoryState::DumpStatistics](#dumpstatistics)|メモリ割り当ての統計を出力、`CMemoryState`オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 `CMemoryState` 構造体は、基本クラスではありません。  
  
 オブジェクトのメモリ ヒープに割り当てが必要でなくなったときに割り当てを解除されない場合に、「メモリ リーク」が発生します。 このようなメモリ リークは、メモリ不足のエラーを最終的に可能性があります。 割り当てるし、プログラムでメモリの割り当てを解除するためのいくつかの方法があります。  
  
-   使用して、 `malloc` / **空き**ランタイム ライブラリからの関数のファミリです。  
  
-   Windows API のメモリ管理関数を使用して**LocalAlloc**/ **LocalFree**と**GlobalAlloc**/ **GlobalFree**.  
  
-   C++ を使用して**新しい**と**削除**演算子。  
  
 `CMemoryState`診断のみ簡単にメモリを検出リークの問題の原因を使用してメモリが割り当てられている場合、**新しい**演算子割り当ては解除されませんを使用して**削除**です。 メモリ管理関数の他の 2 つのグループは、C++ 以外のプログラム、およびこれらを混在させる**新しい**と**削除**同じプログラムではないことをお勧めします。 追加のマクロ`DEBUG_NEW`、置換することは、**新しい**演算子ファイルとのメモリ割り当ての行番号を追跡する必要がある場合。 `DEBUG_NEW` 通常使用されるたびに使用されるが、**新しい**演算子。  
  
 その他の診断と同様、`CMemoryState`診断はのみ、プログラムのデバッグ バージョンで使用できます。 デバッグ バージョンである必要があります、 **_DEBUG**定数を定義します。  
  
 使用することができます、プログラムには、メモリ リークが疑われる場合、 `Checkpoint`、 `Difference`、および`DumpStatistics`プログラム実行中の 2 つのさまざまな時点でのメモリの状態 (割り当てられたオブジェクト) の違いを検出する機能。 この情報は、関数は、割り当てたすべてのオブジェクトをクリーンアップするかどうかの判定に役立ちます。  
  
 単に把握割り当てと解放の不均衡が発生しても十分な情報が提供されない場合を使用できます、`DumpAllObjectsSince`を前の呼び出し以降に割り当てられているすべてのオブジェクトをダンプ関数`Checkpoint`です。 このダンプは、割り当て、ソース ファイルと、オブジェクトが割り当てられた行の順序を示しています。 (を使用している場合`DEBUG_NEW`の割り当て)、およびオブジェクトのアドレスとサイズから派生します。 `DumpAllObjectsSince` オブジェクトごとにも呼び出します`Dump`関数は、現在の状態に関する情報を提供します。  
  
 使用する方法の詳細についての`CMemoryState`し、その他の診断を参照してください[MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)です。  
  
> [!NOTE]
>  型のオブジェクトの宣言`CMemoryState`メンバー関数への呼び出しで囲まれた必要がありますと`#if defined(_DEBUG)/#endif`ディレクティブです。 これにより、メモリ診断は、プログラムのデバッグ ビルドにのみ含まれます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CMemoryState`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afx.h  
  
##  <a name="checkpoint"></a>  CMemoryState::Checkpoint  
 スナップショットのメモリの概要を取得し、この格納`CMemoryState`オブジェクト。  
  
```  
void Checkpoint();
```  
  
### <a name="remarks"></a>Remarks  
 `CMemoryState`メンバー関数[違い](#difference)と[DumpAllObjectsSince](#dumpallobjectssince)このスナップショット データを使用します。  
  
### <a name="example"></a>例  
  例を参照して、[行い](#cmemorystate)コンス トラクターです。  
  
##  <a name="cmemorystate"></a>  CMemoryState::CMemoryState  
 空の構築`CMemoryState`で入力する必要がありますオブジェクト、[チェックポイント](#checkpoint)または[違い](#difference)メンバー関数。  
  
```  
CMemoryState();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]  
  
##  <a name="difference"></a>  CMemoryState::Difference  
 比較する 2 つ`CMemoryState`オブジェクト、し、この違いを格納`CMemoryState`オブジェクト。  
  
```  
BOOL Difference(
    const CMemoryState& oldState,   
    const CMemoryState& newState);
```  
  
### <a name="parameters"></a>パラメーター  
 *oldState*  
 初期のメモリの状態で定義されている、`CMemoryState`チェックポイントです。  
  
 *newState*  
 定義されているメモリの新しい状態、`CMemoryState`チェックポイントです。  
  
### <a name="return-value"></a>戻り値  
 2 つのメモリ状態が異なっている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 [チェックポイント](#checkpoint)2 つのメモリ状態パラメーターごとに呼び出されます必要があります。  
  
### <a name="example"></a>例  
  例を参照して、[行い](#cmemorystate)コンス トラクターです。  
  
##  <a name="dumpallobjectssince"></a>  Cmemorystate::dumpallobjectssince  
 呼び出し、`Dump`クラスから派生した型のすべてのオブジェクトの関数`CObject`を割り当てられている (およびまだ割り当てられている)、最後に[チェックポイント](#checkpoint)この呼び出す`CMemoryState`オブジェクト。  
  
```  
void DumpAllObjectsSince() const;

 
```  
  
### <a name="remarks"></a>Remarks  
 呼び出す`DumpAllObjectsSince`、初期化されていないと`CMemoryState`オブジェクトが現在メモリ内のすべてのオブジェクトをダンプします。  
  
### <a name="example"></a>例  
  例を参照して、[行い](#cmemorystate)コンス トラクターです。  
  
##  <a name="dumpstatistics"></a>  CMemoryState::DumpStatistics  
 レポートを簡潔なメモリ統計情報を出力、`CMemoryState`で塗りつぶされているオブジェクト、[違い](#difference)メンバー関数。  
  
```  
void DumpStatistics() const;

 
```  
  
### <a name="remarks"></a>Remarks  
 レポートに印刷されますが、 [afxDump](diagnostic-services.md#afxdump)デバイス、次に示します。  
  
 サンプル レポートは、数 (または金額) の情報を提供します。  
  
-   空きブロック  
  
-   通常のブロック  
  
-   CRT ブロック  
  
-   ブロックを無視します。  
  
-   クライアント ブロック  
  
-   バイト単位で 1 ついつでも、プログラムによって使用された最大メモリ  
  
-   現在 (バイト) をプログラムによって使用される合計メモリ  
  
 空きブロックが解放が遅れている場合はブロックの数は、`afxMemDF`に設定された**delayFreeMemDF**です。 詳細については、次を参照してください。 [afxMemDF](diagnostic-services.md#afxmemdf)、"MFC マクロとグローバル"セクションでします。 参照してください[デバッグ ヒープ上のブロックの型](http://msdn.microsoft.com/en-us/db2e7f62-0679-4b39-a23f-26f2c2f407c5)のこれらの詳細については、種類をブロックします。  
  
### <a name="example"></a>例  
  次のコードを配置する必要があります*projname*App.cpp です。 次のグローバル変数を定義します。  
  
 [!code-cpp[NVC_MFC_Utilities#40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]  
  
 `InitInstance`関数、行を追加します。  
  
 [!code-cpp[NVC_MFC_Utilities#41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]  
  
 ハンドラーを追加、`ExitInstance`関数し、次のコードを使用します。  
  
 [!code-cpp[NVC_MFC_Utilities#42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]  
  
 出力を表示するデバッグ モードでプログラムを実行できるようになりました、`DumpStatistics`関数。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)



