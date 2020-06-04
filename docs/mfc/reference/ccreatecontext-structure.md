---
title: コンテキスト構造の作成
ms.date: 11/04/2016
f1_keywords:
- CCreateContext
helpviewer_keywords:
- CCreateContext structure [MFC]
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
ms.openlocfilehash: 29fc6210b9888b6a5ba5aaf15b66242c29c15dc8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369377"
---
# <a name="ccreatecontext-structure"></a>コンテキスト構造の作成

フレームワークは、ドキュメント`CCreateContext`に関連付けられたフレーム ウィンドウとビューを作成するときに、この構造を使用します。

## <a name="syntax"></a>構文

```
struct CCreateContext
```

## <a name="remarks"></a>解説

`CCreateContext`は構造体であり、基本クラスを持っていません。

ウィンドウを作成すると、この構造体の値によって、ドキュメントのコンポーネントをデータのビューに接続するために使用される情報が提供されます。 作成プロセスの一部`CCreateContext`をオーバーライドする場合にのみ使用する必要があります。

構造体`CCreateContext`には、ドキュメント、フレーム ウィンドウ、ビュー、およびドキュメント テンプレートへのポインタが含まれます。 また、作成するビューの種類`CRuntimeClass`を識別する を指すポインターも含まれています。 ランタイム クラス情報と現在のドキュメント ポインターを使用して、新しいビューを動的に作成します。 次の表は、各`CCreateContext`メンバーの使用方法と使用方法を示しています。

|メンバー|Type|それは何のためにありますか?|
|------------|----------|--------------------|
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass`をクリックして新しいビューを作成します。|
|`m_pCurrentDoc`|`CDocument*`|新しいビューに関連付ける既存のドキュメント。|
|`m_pNewDocTemplate`|`CDocTemplate*`|新しい MDI フレーム ウィンドウの作成に関連付けられているドキュメント テンプレート。|
|`m_pLastView`|`CView*`|分割ウィンドウ ビューの作成やドキュメントの 2 番目のビューの作成のように、追加ビューをモデル化する元のビュー。|
|`m_pCurrentFrame`|`CFrameWnd*`|ドキュメントに 2 番目のフレーム ウィンドウを作成する場合と同様に、追加のフレーム ウィンドウをモデル化するフレーム ウィンドウ。|

ドキュメント テンプレートは、ドキュメントとその関連コンポーネントを作成するときに、構造に格納されている情報を`CCreateContext`検証します。 たとえば、存在しないドキュメントに対してビューを作成しないでください。

> [!NOTE]
> すべてのポインター`CCreateContext`はオプションであり、未指定または不明の`NULL`場合に使用できます。

`CCreateContext`は、「関連項目」にリストされているメンバー関数によって使用されます。 これらの関数をオーバーライドする場合は、特定の情報については、これらの関数の説明を参照してください。

一般的なガイドラインを次に示します。

- で、ウィンドウ作成の引数として渡される場合、 `CWnd::Create` `CFrameWnd::Create`、`CFrameWnd::LoadFrame`作成コンテキストは、新しいウィンドウの接続先を指定します。 ほとんどのウィンドウでは、構造体全体が省略可能で、`NULL`ポインターを渡すことができます。

- などの`CFrameWnd::OnCreateClient`オーバーライド可能なメンバー関数の`CCreateContext`場合、引数は省略可能です。

- ビューの作成に関係するメンバー関数の場合、ビューを作成するための十分な情報を提供する必要があります。 たとえば、分割ウィンドウの最初のビューでは、ビュー クラス情報と現在のドキュメントを指定する必要があります。

一般に、フレームワークのデフォルトを使用する場合は、`CCreateContext`を無視できます。 高度な変更を試みると、Microsoft Foundation クラス ライブラリのソース コードまたは VIEWEX などのサンプル プログラムが案内されます。 必要なパラメータを忘れると、フレームワーク アサーションによって忘れてしまったものがわかります。

詳細については、MFC`CCreateContext`サンプルの[VIEWEX](../../overview/visual-cpp-samples.md)を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxext.h

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[フレームウンド::作成](../../mfc/reference/cframewnd-class.md#create)<br/>
[フレーム化::ロードフレーム](../../mfc/reference/cframewnd-class.md#loadframe)<br/>
[フレームオンド::オンCreateクライアント](../../mfc/reference/cframewnd-class.md#oncreateclient)<br/>
[スプリッタウンド::作成](../../mfc/reference/csplitterwnd-class.md#create)<br/>
[スプリッタウンド::ビューの作成](../../mfc/reference/csplitterwnd-class.md#createview)<br/>
[CWnd::Create](../../mfc/reference/cwnd-class.md#create)
