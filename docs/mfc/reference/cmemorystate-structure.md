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
ms.openlocfilehash: 823d424620e205d14f247a147bbf7dcb40a626b9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222915"
---
# <a name="cmemorystate-structure"></a>CMemoryState 構造体

プログラムのメモリリークを検出する便利な方法を提供します。

## <a name="syntax"></a>構文

```
struct CMemoryState
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|[説明]|
|----------|-----------------|
|[CMemoryState:: CMemoryState](#cmemorystate)|メモリチェックポイントを制御するクラスに似た構造体を構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|[説明]|
|----------|-----------------|
|[CMemoryState:: Checkpoint](#checkpoint)|現在のメモリ状態のスナップショット (チェックポイント) を取得します。|
|[CMemoryState::D ifference](#difference)|型の2つのオブジェクトの差を計算 `CMemoryState` します。|
|[CMemoryState::D umpAllObjectsSince](#dumpallobjectssince)|前回のチェックポイント以降に現在割り当てられているすべてのオブジェクトの概要をダンプします。|
|[CMemoryState::D umpStatistics](#dumpstatistics)|オブジェクトのメモリ割り当ての統計情報を出力 `CMemoryState` します。|

## <a name="remarks"></a>解説

`CMemoryState`は構造体であり、基本クラスを持っていません。

"メモリリーク" は、オブジェクトのメモリがヒープに割り当てられていて、不要になったときに割り当てが解除されない場合に発生します。 このようなメモリリークが原因で、メモリ不足エラーが発生する可能性があります。 プログラムにメモリを割り当てたり、割り当てを解除したりするには、いくつかの方法があります。

- `malloc` /  `free` ランタイムライブラリの関数ファミリを使用します。

- Windows API のメモリ管理関数、およびを使用し `LocalAlloc` /  `LocalFree` `GlobalAlloc` /  `GlobalFree` ます。

- C++ **`new`** および演算子の使用 **`delete`** 。

診断は、 `CMemoryState` 演算子を使用して割り当てられたメモリがを使用して割り当て解除されない場合に発生するメモリリークの検出にのみ役立ち **`new`** **`delete`** ます。 メモリ管理関数の他の2つのグループは、C + + 以外のプログラム用です **`new`** 。同じプログラムでとを混在させる **`delete`** ことは推奨されません。 **`new`** メモリ割り当てのファイルと行番号の追跡が必要な場合は、演算子を置き換えるために、DEBUG_NEW の追加のマクロが用意されています。 DEBUG_NEW は、通常、演算子を使用するときに使用され **`new`** ます。

他の診断と同様に、 `CMemoryState` 診断はプログラムのデバッグバージョンでのみ使用できます。 デバッグバージョンには _DEBUG 定数が定義されている必要があります。

プログラムにメモリリークが発生していると思われる場合は `Checkpoint` 、、、およびの各関数を使用して、 `Difference` `DumpStatistics` プログラム実行の2つの異なるポイントでのメモリ状態 (割り当てられたオブジェクト) の違いを調べることができます。 この情報は、関数によって割り当てられたすべてのオブジェクトがクリーンアップされるかどうかを判断するのに役立ちます。

割り当てと解放の不均衡が発生している場所を知るだけで十分な情報が得られない場合は、関数を使用して、の `DumpAllObjectsSince` 前回の呼び出し以降に割り当てられたすべてのオブジェクトをダンプでき `Checkpoint` ます。 このダンプは、割り当ての順序、ソースファイルとオブジェクトが割り当てられた行 (割り当てに DEBUG_NEW を使用している場合)、オブジェクトの派生、アドレス、およびそのサイズを示します。 `DumpAllObjectsSince`また `Dump` 、は、各オブジェクトの関数を呼び出して、現在の状態に関する情報を提供します。

およびその他の診断の使用方法の詳細について `CMemoryState` は、「 [MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)」を参照してください。

> [!NOTE]
> 型のオブジェクト `CMemoryState` とメンバー関数への呼び出しの宣言は、ディレクティブで囲む必要があり `#if defined(_DEBUG)/#endif` ます。 これにより、プログラムのデバッグビルドにのみメモリ診断が含まれるようになります。

## <a name="inheritance-hierarchy"></a>継承階層

`CMemoryState`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx

## <a name="cmemorystatecheckpoint"></a><a name="checkpoint"></a>CMemoryState:: Checkpoint

メモリのスナップショットの概要を取得し、このオブジェクトに格納し `CMemoryState` ます。

```cpp
void Checkpoint();
```

### <a name="remarks"></a>解説

`CMemoryState`メンバー関数の[相違点](#difference)と[DumpAllObjectsSince](#dumpallobjectssince)は、このスナップショットデータを使用します。

### <a name="example"></a>例

  [CMemoryState](#cmemorystate)コンストラクターの例を参照してください。

## <a name="cmemorystatecmemorystate"></a><a name="cmemorystate"></a>CMemoryState:: CMemoryState

`CMemoryState`[チェックポイント](#checkpoint)または[差分](#difference)メンバー関数によって入力される必要がある空のオブジェクトを構築します。

```
CMemoryState();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]

## <a name="cmemorystatedifference"></a><a name="difference"></a>CMemoryState::D ifference

2つ `CMemoryState` のオブジェクトを比較し、その差をこのオブジェクトに格納し `CMemoryState` ます。

```
BOOL Difference(
    const CMemoryState& oldState,
    const CMemoryState& newState);
```

### <a name="parameters"></a>パラメーター

*oldState*<br/>
チェックポイントによって定義された初期メモリ状態 `CMemoryState` 。

*newState*<br/>
チェックポイントによって定義された新しいメモリ状態 `CMemoryState` 。

### <a name="return-value"></a>戻り値

2つのメモリ状態が異なる場合は0以外。それ以外の場合は0です。

### <a name="remarks"></a>解説

2つのメモリ状態パラメーターのそれぞれに対して、[チェックポイント](#checkpoint)が呼び出されている必要があります。

### <a name="example"></a>例

  [CMemoryState](#cmemorystate)コンストラクターの例を参照してください。

## <a name="cmemorystatedumpallobjectssince"></a><a name="dumpallobjectssince"></a>CMemoryState::D umpAllObjectsSince

`Dump` `CObject` このオブジェクトの最後の[チェックポイント](#checkpoint)呼び出し以降に割り当てられた (ただし、まだ割り当てられていた) クラスから派生した型のすべてのオブジェクトに対して、関数を呼び出し `CMemoryState` ます。

```cpp
void DumpAllObjectsSince() const;
```

### <a name="remarks"></a>解説

`DumpAllObjectsSince`初期化されていないオブジェクトを使用してを呼び出すと、 `CMemoryState` 現在メモリにあるすべてのオブジェクトがダンプされます。

### <a name="example"></a>例

  [CMemoryState](#cmemorystate)コンストラクターの例を参照してください。

## <a name="cmemorystatedumpstatistics"></a><a name="dumpstatistics"></a>CMemoryState::D umpStatistics

`CMemoryState`[差分](#difference)メンバー関数によって格納されたオブジェクトから、簡潔なメモリ統計レポートを出力します。

```cpp
void DumpStatistics() const;
```

### <a name="remarks"></a>解説

[AfxDump](diagnostic-services.md#afxdump)デバイスに印刷されるレポートには、次のものが表示されます。

サンプルレポートでは、の数 (または金額) に関する情報が提供されます。

- 空きブロック

- 通常のブロック

- CRT ブロック

- ブロックの無視

- クライアント ブロック

- プログラムによって一度に使用される最大メモリ (バイト単位)

- プログラムによって現在使用されているメモリの合計 (バイト単位)

Free ブロックは、がに設定されている場合に、割り当て解除が遅延されたブロックの数です `afxMemDF` `delayFreeMemDF` 。 詳細については、「MFC マクロとグローバル」の「 [afxMemDF](diagnostic-services.md#afxmemdf)」を参照してください。

### <a name="example"></a>例

  次のコードは、 *projname*app.xaml に配置する必要があります。 次のグローバル変数を定義します。

[!code-cpp[NVC_MFC_Utilities#40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]

関数で、 `InitInstance` 次の行を追加します。

[!code-cpp[NVC_MFC_Utilities#41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]

関数のハンドラーを追加 `ExitInstance` し、次のコードを使用します。

[!code-cpp[NVC_MFC_Utilities#42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]

これで、プログラムをデバッグモードで実行し、関数の出力を確認できるようになりました `DumpStatistics` 。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)
