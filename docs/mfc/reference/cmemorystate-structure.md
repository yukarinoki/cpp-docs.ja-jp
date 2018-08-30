---
title: CMemoryState 構造体 |Microsoft Docs
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
ms.openlocfilehash: 348f25718fe22e056da5097bca0d67013a56c4c8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203150"
---
# <a name="cmemorystate-structure"></a>CMemoryState 構造体
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
|[Cmemorystate::checkpoint](#checkpoint)|現在のメモリ状態のスナップショット (チェックポイント) を取得します。|  
|[:Difference](#difference)|型の 2 つのオブジェクト間の差を計算`CMemoryState`します。|  
|[Cmemorystate::dumpallobjectssince](#dumpallobjectssince)|以前のチェックポイント以降には、現在割り当てられているすべてのオブジェクトの概要をダンプします。|  
|[Cmemorystate::dumpstatistics](#dumpstatistics)|メモリ割り当ての統計を出力する`CMemoryState`オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 `CMemoryState` 構造体であり、基底クラスではありません。  
  
 オブジェクトのメモリがヒープに割り当てが必要でなくなったときの割り当て解除されず、「メモリ リーク」が発生します。 このようなメモリ リークは最終的に、メモリ不足のエラーにつながります。 割り当てるし、プログラムでメモリの割り当てを解除するいくつかの方法はあります。  
  
-   使用して、 `malloc` /  `free`ランタイム ライブラリ関数のファミリです。  
  
-   Windows API のメモリ管理関数を使用して`LocalAlloc` /  `LocalFree`と`GlobalAlloc` / `GlobalFree`します。  
  
-   C++ を使用して**新しい**と**削除**演算子。  
  
 `CMemoryState`検出メモリにのみ役立ちます診断を使用してメモリが割り当てられるときに発生するリーク、**新しい**演算子が使用して割り当て解除されません**削除**します。 メモリ管理関数の他の 2 つのグループは、C++ 以外のプログラム、およびで両者を混在させる**新しい**と**削除**同じプログラムでは推奨されません。 置換する追加のマクロ、DEBUG_NEW が提供される、**新しい**演算子と、ファイルとメモリの割り当ての行番号を追跡する必要があります。 DEBUG_NEW が通常使用されるたびに使用される、**新しい**演算子。  
  
 その他の診断と同様、`CMemoryState`診断は、プログラムのデバッグ バージョンで使用可能なだけです。 デバッグ バージョンには、_DEBUG 定数が定義されている必要があります。  
  
 使用することができます、プログラムがメモリ リークが疑われる場合、 `Checkpoint`、 `Difference`、および`DumpStatistics`プログラムの実行の 2 つの異なるポイントでメモリの状態 (割り当てられたオブジェクト) の違いを検出する機能。 この情報は、関数が割り当てたすべてのオブジェクトをクリーンアップするかどうかを決めるのに役立ちます。  
  
 使用することが単に割り当てと解放の不均衡が発生した場所を知ることも十分な情報が提供されていない場合、`DumpAllObjectsSince`以前の呼び出し以降に割り当てられたすべてのオブジェクトをダンプする関数`Checkpoint`します。 このダンプは、割り当て、ソース ファイルと、オブジェクトが割り当てられた場所 (DEBUG_NEW は、割り当てを使用している) 場合、行の順序を示しています。 および、オブジェクト、そのアドレスとそのサイズの派生です。 `DumpAllObjectsSince` オブジェクトごとにも呼び出して`Dump`関数を現在の状態に関する情報を提供します。  
  
 使用する方法の詳細についての`CMemoryState`し、その他の診断を参照してください[MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)します。  
  
> [!NOTE]
>  型のオブジェクトの宣言`CMemoryState`してメンバー関数への呼び出しを囲む必要がありますと`#if defined(_DEBUG)/#endif`ディレクティブ。 これにより、メモリ診断は、プログラムのデバッグ ビルドにのみ含まれます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CMemoryState`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="checkpoint"></a>  Cmemorystate::checkpoint  
 スナップショットのメモリの概要を取得し、これに格納`CMemoryState`オブジェクト。  
  
```  
void Checkpoint();
```  
  
### <a name="remarks"></a>Remarks  
 `CMemoryState`メンバー関数[違い](#difference)と[DumpAllObjectsSince](#dumpallobjectssince)このスナップショット データを使用します。  
  
### <a name="example"></a>例  
  例をご覧ください、 [CMemoryState](#cmemorystate)コンス トラクター。  
  
##  <a name="cmemorystate"></a>  CMemoryState::CMemoryState  
 空を構築します`CMemoryState`オブジェクトが入力する必要がありますが、[チェックポイント](#checkpoint)または[違い](#difference)メンバー関数。  
  
```  
CMemoryState();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]  
  
##  <a name="difference"></a>  :Difference  
 2 つ`CMemoryState`オブジェクト、し、この違いを格納`CMemoryState`オブジェクト。  
  
```  
BOOL Difference(
    const CMemoryState& oldState,   
    const CMemoryState& newState);
```  
  
### <a name="parameters"></a>パラメーター  
 *oldState*  
 メモリの初期状態で定義されている、`CMemoryState`チェックポイントします。  
  
 *newState*  
 定義されている新しいメモリ状態を`CMemoryState`チェックポイントします。  
  
### <a name="return-value"></a>戻り値  
 2 つのメモリ状態が異なっている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 [チェックポイント](#checkpoint)2 つのメモリ状態パラメーターのそれぞれに対して呼び出されてする必要があります。  
  
### <a name="example"></a>例  
  例をご覧ください、 [CMemoryState](#cmemorystate)コンス トラクター。  
  
##  <a name="dumpallobjectssince"></a>  Cmemorystate::dumpallobjectssince  
 呼び出し、`Dump`クラスから派生した型のすべてのオブジェクトの関数`CObject`を割り当てられた (およびまだ割り当てられている)、前回[チェックポイント](#checkpoint)この呼び出す`CMemoryState`オブジェクト。  
  
```  
void DumpAllObjectsSince() const;

 
```  
  
### <a name="remarks"></a>Remarks  
 呼び出す`DumpAllObjectsSince`、初期化されていないと`CMemoryState`オブジェクトが現在メモリ内のすべてのオブジェクトをダンプします。  
  
### <a name="example"></a>例  
  例をご覧ください、 [CMemoryState](#cmemorystate)コンス トラクター。  
  
##  <a name="dumpstatistics"></a>  Cmemorystate::dumpstatistics  
 簡潔なメモリの統計情報レポートを印刷、`CMemoryState`で塗りつぶされているオブジェクト、[違い](#difference)メンバー関数。  
  
```  
void DumpStatistics() const;

 
```  
  
### <a name="remarks"></a>Remarks  
 印刷すると、レポート、 [afxDump](diagnostic-services.md#afxdump)デバイス、次に示します。  
  
 サンプル レポートは、数 (または容量) の情報を提供します。  
  
-   空きブロック  
  
-   通常のブロック  
  
-   CRT ブロック  
  
-   ignore ブロック  
  
-   クライアント ブロック  
  
-   1 つ (バイト) をいつでも、プログラムで使用される最大メモリ  
  
-   現在 (バイト) をプログラムによって使用される合計メモリ  
  
 無料のブロックは、ブロックが割り当て解除が遅延場合数`afxMemDF`に設定された`delayFreeMemDF`します。 詳細については、次を参照してください。 [afxMemDF](diagnostic-services.md#afxmemdf)、"MFC マクロとグローバル"セクションでします。 参照してください[デバッグ ヒープ ブロック型](https://msdn.microsoft.com/db2e7f62-0679-4b39-a23f-26f2c2f407c5)の詳細については、これらの種類をブロックするのです。  
  
### <a name="example"></a>例  
  次のコードを配置する必要があります*projname*App.cpp します。 次のグローバル変数を定義します。  
  
 [!code-cpp[NVC_MFC_Utilities#40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]  
  
 `InitInstance`関数、行を追加します。  
  
 [!code-cpp[NVC_MFC_Utilities#41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]  
  
 ハンドラーを追加、`ExitInstance`関数を次のコードを使用します。  
  
 [!code-cpp[NVC_MFC_Utilities#42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]  
  
 ここでの出力を表示するデバッグ モードでプログラムを実行することができます、`DumpStatistics`関数。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)



