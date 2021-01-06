---
description: '詳細情報: CWaitCursor クラス'
title: CWaitCursor クラス
ms.date: 11/04/2016
f1_keywords:
- CWaitCursor
- AFXWIN/CWaitCursor
- AFXWIN/CWaitCursor::CWaitCursor
- AFXWIN/CWaitCursor::Restore
helpviewer_keywords:
- CWaitCursor [MFC], CWaitCursor
- CWaitCursor [MFC], Restore
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
ms.openlocfilehash: 5d2323e3be78154c6a9d3ded55ab9e1a951d78b7
ms.sourcegitcommit: 6183207b11575d7b44ebd7c18918e916a0d8c63d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "97951498"
---
# <a name="cwaitcursor-class"></a>CWaitCursor クラス

時間がかかる処理を実行している最中に、通常は砂時計として表示される待機カーソルを表示する 1 つの方法を提供します。

## <a name="syntax"></a>構文

```
class CWaitCursor
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CWaitCursor::CWaitCursor](#cwaitcursor)|オブジェクトを構築 `CWaitCursor` し、待機カーソルを表示します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CWaitCursor:: Restore](#restore)|変更された待機カーソルを復元します。|

## <a name="remarks"></a>解説

`CWaitCursor` に基底クラスがありません。

優れた Windows プログラミング手法を使用するには、時間がかかる操作を実行するたびに待機カーソルを表示する必要があります。

待機カーソルを表示するには、時間の `CWaitCursor` かかる操作を実行するコードの前に変数を定義するだけです。 オブジェクトのコンストラクターによって自動的に待機カーソルが表示されます。

オブジェクトがスコープ外に出ると ( `CWaitCursor` オブジェクトが宣言されているブロックの末尾)、そのデストラクターはカーソルを前のカーソルに設定します。 つまり、オブジェクトは、必要なクリーンアップを自動的に実行します。

> [!NOTE]
> コンストラクターとデストラクターがどのように動作するかによっ `CWaitCursor` て、オブジェクトは常にローカル変数として宣言されます。グローバル変数として宣言されることも、で割り当てられることもありません **`new`** 。

メッセージボックスやダイアログボックスの表示など、カーソルが変更される可能性のある操作を実行する場合は、 [restore](#restore) メンバー関数を呼び出して待機カーソルを復元します。 `Restore`待機カーソルが現在表示されている場合でも、を呼び出すことはできます。

待機カーソルを表示するもう1つの方法は、 [ccmdtarget:: BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)、 [Ccmdtarget:: EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)、および [RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)の組み合わせを使用することです。 ただし、 `CWaitCursor` 長い操作が終了したときにカーソルを前のカーソルに設定する必要がないため、を使用する方が簡単です。

> [!NOTE]
> MFC では、 [CWinApp::D oWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor) 仮想関数を使用してカーソルを設定し、復元します。 この関数をオーバーライドして、カスタム動作を提供できます。

## <a name="inheritance-hierarchy"></a>継承階層

`CWaitCursor`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#62](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_1.cpp)]

## <a name="cwaitcursorcwaitcursor"></a><a name="cwaitcursor"></a> CWaitCursor::CWaitCursor

待機カーソルを表示するには、時間の `CWaitCursor` かかる操作を実行するコードの前にオブジェクトを宣言するだけです。

```
CWaitCursor();
```

### <a name="remarks"></a>解説

コンストラクターによって自動的に待機カーソルが表示されます。

オブジェクトがスコープ外に出ると ( `CWaitCursor` オブジェクトが宣言されているブロックの末尾)、そのデストラクターはカーソルを前のカーソルに設定します。 つまり、オブジェクトは、必要なクリーンアップを自動的に実行します。

ブロックの最後 (関数の末尾の前) でデストラクターが呼び出され、待機カーソルが関数の一部でアクティブになるという事実を利用できます。このような場合は、 この手法については、次の2番目の例を参照してください。

> [!NOTE]
> コンストラクターとデストラクターがどのように動作するかによっ `CWaitCursor` て、オブジェクトは常にローカル変数として宣言されます。グローバル変数として宣言されることも、で割り当てられることもありません **`new`** 。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#63](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_2.cpp)]

## <a name="cwaitcursorrestore"></a><a name="restore"></a> CWaitCursor:: Restore

待機カーソルを復元するには、メッセージボックスやダイアログボックスの表示などの操作を実行した後に、この関数を呼び出します。これにより、待機カーソルが別のカーソルに変わる可能性があります。

```cpp
void Restore();
```

### <a name="remarks"></a>解説

`Restore`待機カーソルが現在表示されている場合でも、を呼び出すことはできます。

オブジェクトが宣言されている関数以外の関数で待機カーソルを復元する必要がある場合は `CWaitCursor` 、 [CCmdTarget:: RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)を呼び出すことができます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#64](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_3.cpp)]

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget:: BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)<br/>
[CCmdTarget:: EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)<br/>
[CCmdTarget:: RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)<br/>
[CWinApp::D oWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)<br/>
[を使用して MFC でウィンドウのマウスポインターを変更する Visual C++](/troubleshoot/cpp/change-mouse-pointer-window-mfc)
