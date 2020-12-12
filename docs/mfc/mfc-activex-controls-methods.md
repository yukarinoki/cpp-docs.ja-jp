---
description: '詳細については、「MFC ActiveX コントロール: メソッド」を参照してください。'
title: 'MFC ActiveX コントロール : メソッド'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], methods
ms.assetid: e20271de-6ffa-4ba0-848b-bafe6c9e510c
ms.openlocfilehash: 27e56653e8a3cf3ebd7ab182b633a1c3ba0b99b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236933"
---
# <a name="mfc-activex-controls-methods"></a>MFC ActiveX コントロール : メソッド

ActiveX コントロールは、自身とそのコントロールコンテナーの間で通信するためのイベントを発生させます。 コンテナーは、メソッドとプロパティを使用してコントロールと通信することもできます。 メソッドは関数とも呼ばれます。

メソッドとプロパティは、オートメーションクライアントや ActiveX コントロールコンテナーなど、他のアプリケーションで使用するためにエクスポートされたインターフェイスを提供します。 ActiveX コントロールのプロパティの詳細については、「 [MFC Activex コントロール: プロパティ](mfc-activex-controls-properties.md)」を参照してください。

メソッドは、C++ クラスのメンバー関数とよく似ています。 コントロールで実装できるメソッドには、ストックと custom の2種類があります。 Stock イベントと同様に、メソッドは、 [COleControl](reference/colecontrol-class.md) が実装を提供するメソッドです。 ストックメソッドの詳細については、「 [MFC ActiveX コントロール: ストックメソッドの追加](mfc-activex-controls-adding-stock-methods.md)」を参照してください。 開発者によって定義されたカスタムメソッドによって、コントロールの追加のカスタマイズが可能になります。 詳細については、「 [MFC ActiveX コントロール: カスタムメソッドの追加](mfc-activex-controls-adding-custom-methods.md)」を参照してください。

Microsoft Foundation Class ライブラリ (MFC) は、コントロールでストックおよびカスタムメソッドをサポートできるようにするメカニズムを実装しています。 最初の部分はクラス `COleControl` です。 から派生 `CWnd` し `COleControl` たメンバー関数は、すべての ActiveX コントロールに共通のストックメソッドをサポートしています。 このメカニズムの2番目の部分はディスパッチマップです。 ディスパッチマップは、メッセージマップに似ています。ただし、関数を Windows メッセージ ID にマップするのではなく、ディスパッチマップによって、仮想メンバー関数が IDispatch ID にマップされます。

コントロールがさまざまなメソッドを適切にサポートするためには、そのクラスがディスパッチマップを宣言する必要があります。 これは、コントロールクラスヘッダー () にある次のコード行によって実現されます。H) ファイル:

[!code-cpp[NVC_MFC_AxUI#13](codesnippet/cpp/mfc-activex-controls-methods_1.h)]

ディスパッチマップの主な目的は、外部の呼び出し元 (コンテナーなど) によって使用されるメソッド名と、メソッドを実装するコントロールのクラスのメンバー関数との間の関係を確立することです。 ディスパッチマップが宣言されたら、コントロールの実装 () で定義する必要があります。CPP) ファイル。 次のコード行では、ディスパッチマップを定義しています。

[!code-cpp[NVC_MFC_AxUI#14](codesnippet/cpp/mfc-activex-controls-methods_2.cpp)]
[!code-cpp[NVC_MFC_AxUI#15](codesnippet/cpp/mfc-activex-controls-methods_3.cpp)]

[MFC ActiveX コントロールウィザード](reference/mfc-activex-control-wizard.md)を使用してプロジェクトを作成した場合は、これらの行が自動的に追加されています。 MFC ActiveX コントロールウィザードが使用されていない場合は、これらの行を手動で追加する必要があります。

次の記事では、メソッドについて詳しく説明します。

- [MFC ActiveX コントロール: ストックメソッドの追加](mfc-activex-controls-adding-stock-methods.md)

- [MFC ActiveX コントロール: カスタムメソッドの追加](mfc-activex-controls-adding-custom-methods.md)

- [MFC ActiveX コントロール: メソッドからエラーコードを返す](mfc-activex-controls-returning-error-codes-from-a-method.md)

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)
