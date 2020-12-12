---
description: '詳細については、次を参照してください: CCreateContext 構造体'
title: CCreateContext 構造体
ms.date: 11/04/2016
f1_keywords:
- CCreateContext
helpviewer_keywords:
- CCreateContext structure [MFC]
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
ms.openlocfilehash: b0d8c3a38d4d6ce9ee6130092ea6b27a50ed15e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220462"
---
# <a name="ccreatecontext-structure"></a>CCreateContext 構造体

フレームワークは、 `CCreateContext` ドキュメントに関連付けられているフレームウィンドウとビューを作成するときに、構造体を使用します。

## <a name="syntax"></a>構文

```
struct CCreateContext
```

## <a name="remarks"></a>解説

`CCreateContext` は構造体であり、基本クラスを持っていません。

ウィンドウを作成すると、この構造体の値は、ドキュメントのコンポーネントをそのデータのビューに接続するために使用される情報を提供します。 を使用する必要がある `CCreateContext` のは、作成プロセスの一部をオーバーライドする場合のみです。

構造体には、 `CCreateContext` ドキュメント、フレームウィンドウ、ビュー、およびドキュメントテンプレートへのポインターが含まれています。 また、 `CRuntimeClass` 作成するビューの種類を識別するへのポインターも含まれています。 新しいビューを動的に作成するには、ランタイムクラス情報と現在のドキュメントポインターを使用します。 次の表では、各メンバーがどのように使用されるかを示し `CCreateContext` ます。

|メンバー|種類|目的|
|------------|----------|--------------------|
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass` 作成する新しいビューの。|
|`m_pCurrentDoc`|`CDocument*`|新しいビューに関連付けられる既存のドキュメント。|
|`m_pNewDocTemplate`|`CDocTemplate*`|新しい MDI フレームウィンドウの作成に関連付けられているドキュメントテンプレート。|
|`m_pLastView`|`CView*`|分割ウィンドウビューの作成やドキュメントでの2番目のビューの作成と同様に、追加のビューをモデル化する元のビュー。|
|`m_pCurrentFrame`|`CFrameWnd*`|ドキュメント上に2つ目のフレームウィンドウを作成する場合と同様に、追加のフレームウィンドウがモデル化されるフレームウィンドウ。|

ドキュメントテンプレートは、ドキュメントとそれに関連付けられたコンポーネントを作成するときに、構造に格納されている情報を検証し `CCreateContext` ます。 たとえば、存在しないドキュメントに対してビューを作成することはできません。

> [!NOTE]
> 内のすべてのポインター `CCreateContext` は省略可能であり、指定されて `NULL` いないか不明である場合があります。

`CCreateContext` は、「参照」に記載されているメンバー関数によって使用されます。 オーバーライドする予定の場合は、これらの関数の説明を参照してください。

いくつかの一般的なガイドラインを次に示します。

- 、、などのように、ウィンドウ作成の引数として渡された場合、 `CWnd::Create` `CFrameWnd::Create` `CFrameWnd::LoadFrame` 作成コンテキストは新しいウィンドウの接続先を指定します。 ほとんどのウィンドウでは、構造体全体は省略可能であり、 `NULL` ポインターを渡すことができます。

- などのオーバーライド可能なメンバー関数の場合、 `CFrameWnd::OnCreateClient` `CCreateContext` 引数は省略可能です。

- ビューの作成に関係するメンバー関数の場合は、ビューを作成するための十分な情報を提供する必要があります。 たとえば、スプリッターウィンドウの最初のビューでは、ビュークラスの情報と現在のドキュメントを指定する必要があります。

一般に、フレームワークの既定値を使用する場合は、を無視でき `CCreateContext` ます。 さらに高度な変更を行う場合は、Microsoft Foundation Class ライブラリソースコードまたはサンプルプログラム (VIEWEX など) に従ってください。 必須パラメーターを忘れた場合、フレームワークのアサーションによって、忘れたものが通知されます。

の詳細については `CCreateContext` 、MFC のサンプル [VIEWEX](../../overview/visual-cpp-samples.md)を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** afxext.h

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd:: Create](../../mfc/reference/cframewnd-class.md#create)<br/>
[CFrameWnd:: LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)<br/>
[CFrameWnd:: OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)<br/>
[CSplitterWnd:: Create](../../mfc/reference/csplitterwnd-class.md#create)<br/>
[CSplitterWnd:: CreateView](../../mfc/reference/csplitterwnd-class.md#createview)<br/>
[CWnd::Create](../../mfc/reference/cwnd-class.md#create)
