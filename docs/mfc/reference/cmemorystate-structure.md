---
title: CMemoryState 構造体
ms.date: 11/04/2016
f1_keywords:
- CMemoryState
helpviewer_keywords:
- CMemoryState structure [MFC]
- memory leaks [MFC], detecting
- detecting memory leaks [MFC]
ms.assetid: 229d9de7-a6f3-4cc6-805b-5a9d9b1bfe1d
ms.openlocfilehash: 94a2fb65a9a3030f9dc683d0eb30f476b9de1cad
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752616"
---
# <a name="cmemorystate-structure"></a>CMemoryState 構造体

プログラムのメモリ リークを検出する便利な方法を提供します。

## <a name="syntax"></a>構文

```
struct CMemoryState
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[状態::Cメモリ状態](#cmemorystate)|メモリ チェックポイントを制御するクラスに似た構造体を構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[チェックポイント状態::チェックポイント](#checkpoint)|現在のメモリ状態のスナップショット (チェックポイント) を取得します。|
|[Cメモリ状態::D推論](#difference)|型の 2 つのオブジェクトの差`CMemoryState`を計算します。|
|[Cメモリ状態::Dのオブジェクト](#dumpallobjectssince)|直前のチェックポイント以降に現在割り当てられているすべてのオブジェクトの要約をダンプします。|
|[状態::Dウンプ統計](#dumpstatistics)|オブジェクトのメモリ割り当て`CMemoryState`統計を出力します。|

## <a name="remarks"></a>解説

`CMemoryState`は構造体であり、基本クラスを持っていません。

"メモリ リーク" は、オブジェクトのメモリがヒープに割り当てられ、不要になった場合には割り当て解除されない場合に発生します。 このようなメモリ リークは、最終的にメモリ不足エラーにつながる可能性があります。 プログラムでメモリを割り当てる方法と割り当てを解除するには、いくつかの方法があります。

- ランタイム`malloc`/ `free`ライブラリの関数ファミリを使用する。

- Windows API のメモリ管理機能を`LocalAlloc`/ `LocalFree`使用`GlobalAlloc`/ `GlobalFree`して、 と .

- C++ の**新規**および**削除**演算子を使用する。

この`CMemoryState`診断は **、new**演算子を使用して割り当てられたメモリが**delete**を使用して割り当て解除されていない場合に発生したメモリ リークを検出する場合にのみ役立ちます。 メモリ管理機能の他の 2 つのグループは非 C++ プログラム用であり、それらを同じプログラムで**の新規**および**削除**と混合することはお勧めしません。 メモリ割り当てのファイルと行番号の追跡が必要な場合に **、新しい**演算子を置き換えるために、DEBUG_NEW追加のマクロが提供されます。 DEBUG_NEWは、通常は**new**演算子を使用する場合に必ず使用されます。

他の診断と同様に`CMemoryState`、診断はプログラムのデバッグ バージョンでのみ使用できます。 デバッグ バージョンには、_DEBUG定数が定義されている必要があります。

プログラムにメモリ リークが発生していると思われる場合は、 `Checkpoint`、`Difference`および`DumpStatistics`関数を使用して、プログラム実行の 2 つの異なるポイントにおけるメモリ状態 (割り当てられたオブジェクト) の違いを検出できます。 この情報は、関数が割り当てたすべてのオブジェクトをクリーンアップしているかどうかを判断する際に役立ちます。

割り当てと割り当て解除の不均衡が発生した場所を知っているだけでは十分`DumpAllObjectsSince`な情報が得られていない場合は、この関数を使用`Checkpoint`して、 に対する前回の呼び出し以降に割り当てられたすべてのオブジェクトをダンプできます。 このダンプには、割り当ての順序、オブジェクトが割り当てられたソース・ファイルと行 (割り当てに DEBUG_NEWを使用している場合)、オブジェクトの派生、アドレス、およびサイズが示されます。 `DumpAllObjectsSince`また、各オブジェクトの関数`Dump`を呼び出して、現在の状態に関する情報を提供します。

その他の診断の使用方法`CMemoryState`の詳細については、「 MFC[アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)」を参照してください。

> [!NOTE]
> 型`CMemoryState`のオブジェクトの宣言とメンバー関数の呼び出しは、ディレクティブ`#if defined(_DEBUG)/#endif`で囲む必要があります。 これにより、メモリ診断はプログラムのデバッグ ビルドにのみ含まれます。

## <a name="inheritance-hierarchy"></a>継承階層

`CMemoryState`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="cmemorystatecheckpoint"></a><a name="checkpoint"></a>チェックポイント状態::チェックポイント

メモリのスナップショットの概要を取得し、この`CMemoryState`オブジェクトに格納します。

```cpp
void Checkpoint();
```

### <a name="remarks"></a>解説

この`CMemoryState`スナップショット データを使用するメンバー関数[の相違](#difference)と[DumpAllObjects 以降](#dumpallobjectssince)。

### <a name="example"></a>例

  [CMemoryState](#cmemorystate)コンストラクターの例を参照してください。

## <a name="cmemorystatecmemorystate"></a><a name="cmemorystate"></a>状態::Cメモリ状態

[チェックポイント](#checkpoint)または[相違点](#difference)の`CMemoryState`メンバー関数で入力する必要がある空のオブジェクトを構築します。

```
CMemoryState();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]

## <a name="cmemorystatedifference"></a><a name="difference"></a>Cメモリ状態::D推論

2 つの`CMemoryState`オブジェクトを比較し、その差を`CMemoryState`このオブジェクトに格納します。

```
BOOL Difference(
    const CMemoryState& oldState,
    const CMemoryState& newState);
```

### <a name="parameters"></a>パラメーター

*古い状態*<br/>
`CMemoryState`チェックポイントで定義された初期メモリ状態。

*newState*<br/>
`CMemoryState`チェックポイントで定義された新しいメモリ状態。

### <a name="return-value"></a>戻り値

2 つのメモリ状態が異なる場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

[チェックポイント](#checkpoint)は、2 つのメモリ状態パラメータのそれぞれに対して呼び出されている必要があります。

### <a name="example"></a>例

  [CMemoryState](#cmemorystate)コンストラクターの例を参照してください。

## <a name="cmemorystatedumpallobjectssince"></a><a name="dumpallobjectssince"></a>Cメモリ状態::Dのオブジェクト

この`CMemoryState`オブジェクト`Dump`に対する最後の[チェックポイント](#checkpoint)呼び出し`CObject`以降に割り当てられた (割り当てられた) クラスから派生した型のすべてのオブジェクトの関数を呼び出します。

```cpp
void DumpAllObjectsSince() const;
```

### <a name="remarks"></a>解説

初期化`DumpAllObjectsSince``CMemoryState`されていないオブジェクトを使用して呼び出すと、現在メモリ内にあるすべてのオブジェクトがダンプされます。

### <a name="example"></a>例

  [CMemoryState](#cmemorystate)コンストラクターの例を参照してください。

## <a name="cmemorystatedumpstatistics"></a><a name="dumpstatistics"></a>状態::Dウンプ統計

Difference メンバー関数によって埋め込まれたオブジェクトから、`CMemoryState`簡潔なメモリ統計レポートを[Difference](#difference)出力します。

```cpp
void DumpStatistics() const;
```

### <a name="remarks"></a>解説

[afxDump](diagnostic-services.md#afxdump)デバイスに出力されるレポートには、次の情報が表示されます。

サンプル レポートには、次の数 (または量) に関する情報が表示されます。

- 無料ブロック

- 通常のブロック

- CRT ブロック

- ブロックを無視する

- クライアント ブロック

- プログラムが一度に使用する最大メモリ (バイト単位)

- プログラムが現在使用している合計メモリ (バイト単位)

フリーブロックは、割り当て解除がに設定されている`afxMemDF`場合に遅延`delayFreeMemDF`したブロックの数です。 詳細については、「MFC マクロとグローバル」セクションの[afxMemDF](diagnostic-services.md#afxmemdf)を参照してください。

### <a name="example"></a>例

  次のコードは *、projname*App.cpp に配置する必要があります。 次のグローバル変数を定義します。

[!code-cpp[NVC_MFC_Utilities#40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]

関数で`InitInstance`、次の行を追加します。

[!code-cpp[NVC_MFC_Utilities#41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]

関数のハンドラーを`ExitInstance`追加し、次のコードを使用します。

[!code-cpp[NVC_MFC_Utilities#42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]

デバッグ モードでプログラムを実行して、関数の出力を`DumpStatistics`確認できるようになりました。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)
