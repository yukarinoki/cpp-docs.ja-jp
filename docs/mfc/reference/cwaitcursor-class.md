---
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
ms.openlocfilehash: 48ef8f9c965f54deafcc62451639f8c31021e900
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373177"
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
|[カーソルを待つ](#cwaitcursor)|オブジェクトを`CWaitCursor`構築し、待機カーソルを表示します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[カーソルを置く::復元](#restore)|変更後に待機カーソルを復元します。|

## <a name="remarks"></a>解説

`CWaitCursor`は基本クラスを持っていません。

Windows プログラミングの良い方法では、時間の経過に応じて操作を実行する場合は、待機カーソルを表示する必要があります。

待機カーソルを表示するには、長い操作`CWaitCursor`を実行するコードの前に変数を定義するだけです。 オブジェクトのコンストラクターによって、待機カーソルが自動的に表示されます。

オブジェクトがスコープ外に出ると (`CWaitCursor`オブジェクトが宣言されているブロックの最後)、そのデストラクターはカーソルを前のカーソルに設定します。 つまり、オブジェクトは必要なクリーンアップを自動的に実行します。

> [!NOTE]
> コンストラクタとデストラクタの動作により、`CWaitCursor`オブジェクトは常にローカル変数として宣言され、グローバル変数として宣言されることも **、new**.

メッセージ ボックスやダイアログ ボックスの表示など、カーソルが変更される可能性のある操作を実行する場合は[、Restore](#restore)メンバー関数を呼び出して待機カーソルを復元します。 待機カーソルが現在表示`Restore`されている場合でも、呼び出しは大丈夫です。

待機カーソルを表示するもう 1 つの方法は[、CCmdTarget:::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor) [、CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)、およびおそらく[CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)の組み合わせを使用することです。 ただし、`CWaitCursor`時間のかかる操作を完了したときにカーソルを前のカーソルに設定する必要がないため、使いやすくなります。

> [!NOTE]
> MFC は[、CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)仮想関数を使用してカーソルを設定および復元します。 この関数をオーバーライドして、カスタム動作を提供できます。

## <a name="inheritance-hierarchy"></a>継承階層

`CWaitCursor`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#62](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_1.cpp)]

## <a name="cwaitcursorcwaitcursor"></a><a name="cwaitcursor"></a>カーソルを待つ

待機カーソルを表示するには、長い操作`CWaitCursor`を実行するコードの前にオブジェクトを宣言するだけです。

```
CWaitCursor();
```

### <a name="remarks"></a>解説

コンストラクターによって、待機カーソルが自動的に表示されます。

オブジェクトがスコープ外に出ると (`CWaitCursor`オブジェクトが宣言されているブロックの最後)、そのデストラクターはカーソルを前のカーソルに設定します。 つまり、オブジェクトは必要なクリーンアップを自動的に実行します。

関数の一部でのみ待機カーソルをアクティブにするために、ブロックの最後 (関数の末尾の前にある場合があります) でデストラクターが呼び出されるという事実を利用できます。 この手法は、次の 2 番目の例に示します。

> [!NOTE]
> コンストラクタとデストラクタの動作により、`CWaitCursor`オブジェクトは常にローカル変数として宣言され、グローバル変数として宣言されることも **、new**.

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#63](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_2.cpp)]

## <a name="cwaitcursorrestore"></a><a name="restore"></a>カーソルを置く::復元

待機カーソルを復元するには、メッセージ ボックスやダイアログ ボックスの表示など、操作の実行後にこの関数を呼び出します。

```
void Restore();
```

### <a name="remarks"></a>解説

待機カーソルが現在表示`Restore`されている場合でも呼び出しは OK です。

`CWaitCursor`オブジェクトが宣言されている関数以外の関数で待機カーソルを復元する必要がある場合は[、CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)を呼び出すことができます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#64](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_3.cpp)]

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[を開始します。](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)<br/>
[をクリックします。](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)<br/>
[をクリックします。](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)<br/>
[クウィナップ::Dウェイトカーソル](../../mfc/reference/cwinapp-class.md#dowaitcursor)<br/>
[方法: Microsoft Foundation クラス アプリケーションでマウス カーソルを変更する](https://go.microsoft.com/fwlink/p/?linkid=128044)
