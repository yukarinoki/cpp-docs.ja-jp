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
ms.openlocfilehash: a110e1345cb970c117de125bd8105e1bc86eaf94
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79426139"
---
# <a name="cmemorystate-structure"></a>CMemoryState 構造体

プログラムのメモリリークを検出する便利な方法を提供します。

## <a name="syntax"></a>構文

```
struct CMemoryState
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|Description|
|----------|-----------------|
|[CMemoryState:: CMemoryState](#cmemorystate)|メモリチェックポイントを制御するクラスに似た構造体を構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[CMemoryState:: Checkpoint](#checkpoint)|現在のメモリ状態のスナップショット (チェックポイント) を取得します。|
|[CMemoryState::D ifference](#difference)|`CMemoryState`型の2つのオブジェクトの差を計算します。|
|[CMemoryState::D umpAllObjectsSince](#dumpallobjectssince)|前回のチェックポイント以降に現在割り当てられているすべてのオブジェクトの概要をダンプします。|
|[CMemoryState::D umpStatistics](#dumpstatistics)|`CMemoryState` オブジェクトのメモリ割り当ての統計を出力します。|

## <a name="remarks"></a>解説

`CMemoryState` は構造体であり、基本クラスを持ちません。

"メモリリーク" は、オブジェクトのメモリがヒープに割り当てられていて、不要になったときに割り当てが解除されない場合に発生します。 このようなメモリリークが原因で、メモリ不足エラーが発生する可能性があります。 プログラムにメモリを割り当てたり、割り当てを解除したりするには、いくつかの方法があります。

- `malloc`/ 使用して、ランタイムライブラリの関数の `free` ファミリを使用します。

- Windows API のメモリ管理関数を使用すると、`LocalAlloc`/ `LocalFree` と `GlobalAlloc`/ `GlobalFree`ます。

- C++ **New**演算子と**delete**演算子を使用します。

`CMemoryState` 診断は、 **new**演算子を使用して割り当てられたメモリが**delete**を使用して割り当て解除されない場合に発生するメモリリークの検出にのみ役立ちます。 他の2つのメモリ管理関数は、C++プログラム以外では使用できません。また、同じプログラムで**new**と**delete**を混在させることはお勧めしません。 メモリ割り当てのファイルと行番号の追跡が必要な場合は、 **NEW**演算子を置き換えるために、DEBUG_NEW の追加のマクロが用意されています。 DEBUG_NEW は、通常**NEW**演算子を使用するときに常に使用されます。

他の診断と同様に、`CMemoryState` 診断は、プログラムのデバッグバージョンでのみ使用できます。 デバッグバージョンには _DEBUG 定数が定義されている必要があります。

プログラムにメモリリークが発生していると思われる場合は、`Checkpoint`、`Difference`、および `DumpStatistics` の各関数を使用して、プログラム実行の2つの異なるポイントでのメモリ状態 (割り当てられたオブジェクト) の違いを検出できます。 この情報は、関数によって割り当てられたすべてのオブジェクトがクリーンアップされるかどうかを判断するのに役立ちます。

割り当てと解放の不均衡が発生している場所を知るだけで十分な情報が得られない場合は、`DumpAllObjectsSince` 関数を使用して、前の `Checkpoint`の呼び出し以降に割り当てられたすべてのオブジェクトをダンプできます。 このダンプは、割り当ての順序、ソースファイルとオブジェクトが割り当てられた行 (割り当てに DEBUG_NEW を使用している場合)、オブジェクトの派生、アドレス、およびそのサイズを示します。 また `DumpAllObjectsSince` は、各オブジェクトの `Dump` 関数を呼び出して、現在の状態に関する情報を提供します。

`CMemoryState` およびその他の診断の使用方法の詳細については、「 [MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)」を参照してください。

> [!NOTE]
>  `CMemoryState` 型のオブジェクトの宣言とメンバー関数の呼び出しは、`#if defined(_DEBUG)/#endif` ディレクティブで囲む必要があります。 これにより、プログラムのデバッグビルドにのみメモリ診断が含まれるようになります。

## <a name="inheritance-hierarchy"></a>継承階層

`CMemoryState`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

##  <a name="checkpoint"></a>CMemoryState:: Checkpoint

メモリのスナップショットの概要を取得し、この `CMemoryState` オブジェクトに格納します。

```
void Checkpoint();
```

### <a name="remarks"></a>解説

`CMemoryState` メンバー関数の[違い](#difference)と[DumpAllObjectsSince](#dumpallobjectssince)は、このスナップショットデータを使用します。

### <a name="example"></a>例

  [CMemoryState](#cmemorystate)コンストラクターの例を参照してください。

##  <a name="cmemorystate"></a>CMemoryState:: CMemoryState

[チェックポイント](#checkpoint)または[差分](#difference)メンバー関数によって入力する必要がある空の `CMemoryState` オブジェクトを構築します。

```
CMemoryState();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]

##  <a name="difference"></a>CMemoryState::D ifference

2つの `CMemoryState` オブジェクトを比較し、その違いをこの `CMemoryState` オブジェクトに格納します。

```
BOOL Difference(
    const CMemoryState& oldState,
    const CMemoryState& newState);
```

### <a name="parameters"></a>パラメーター

*oldState*<br/>
`CMemoryState` チェックポイントによって定義される初期メモリ状態。

*newState*<br/>
`CMemoryState` チェックポイントによって定義された新しいメモリ状態。

### <a name="return-value"></a>戻り値

2つのメモリ状態が異なる場合は0以外。それ以外の場合は0です。

### <a name="remarks"></a>解説

2つのメモリ状態パラメーターのそれぞれに対して、[チェックポイント](#checkpoint)が呼び出されている必要があります。

### <a name="example"></a>例

  [CMemoryState](#cmemorystate)コンストラクターの例を参照してください。

##  <a name="dumpallobjectssince"></a>CMemoryState::D umpAllObjectsSince

この `CMemoryState` オブジェクトの最後の[チェックポイント](#checkpoint)呼び出し以降に割り当てられた (ただし、まだ割り当てられている) `CObject` クラスから派生した型のすべてのオブジェクトに対して、`Dump` 関数を呼び出します。

```
void DumpAllObjectsSince() const;
```

### <a name="remarks"></a>解説

初期化されていない `CMemoryState` オブジェクトを使用して `DumpAllObjectsSince` を呼び出すと、現在メモリにあるすべてのオブジェクトがダンプされます。

### <a name="example"></a>例

  [CMemoryState](#cmemorystate)コンストラクターの例を参照してください。

##  <a name="dumpstatistics"></a>CMemoryState::D umpStatistics

[差分](#difference)メンバー関数によって入力された `CMemoryState` オブジェクトから簡潔なメモリ統計レポートを出力します。

```
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

Free ブロックは、`afxMemDF` が `delayFreeMemDF`に設定されている場合に、割り当て解除が遅延されたブロックの数です。 詳細については、「MFC マクロとグローバル」の「 [afxMemDF](diagnostic-services.md#afxmemdf)」を参照してください。

### <a name="example"></a>例

  次のコードは、 *projname*app.xaml に配置する必要があります。 次のグローバル変数を定義します。

[!code-cpp[NVC_MFC_Utilities#40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]

`InitInstance` 関数で、次の行を追加します。

[!code-cpp[NVC_MFC_Utilities#41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]

`ExitInstance` 関数のハンドラーを追加し、次のコードを使用します。

[!code-cpp[NVC_MFC_Utilities#42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]

これで、プログラムをデバッグモードで実行し、`DumpStatistics` 関数の出力を確認できるようになりました。

## <a name="see-also"></a>参照

[階層図](../../mfc/hierarchy-chart.md)
