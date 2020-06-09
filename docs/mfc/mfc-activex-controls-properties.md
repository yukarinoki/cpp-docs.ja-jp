---
title: 'MFC ActiveX コントロール : プロパティ'
ms.date: 11/04/2016
helpviewer_keywords:
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
- properties [MFC]
ms.assetid: b678a53c-0d9e-476f-8aa0-23b80baaba46
ms.openlocfilehash: c7ed0fddea660409f5089159b71d39a29b01d538
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618180"
---
# <a name="mfc-activex-controls-properties"></a>MFC ActiveX コントロール : プロパティ

ActiveX コントロールは、コントロールコンテナーと通信するためのイベントを発生させます。 返されるコンテナーは、メソッドとプロパティを使用してコントロールと通信します。 メソッドとプロパティは、それぞれ、C++ クラスのメンバー関数とメンバー変数に対して、使用と目的に似ています。 プロパティは、任意のコンテナーに公開されている ActiveX コントロールのデータメンバーです。 プロパティは、オートメーションクライアントや ActiveX コントロールコンテナーなどの ActiveX コントロールを含むアプリケーションのインターフェイスを提供します。

プロパティは、属性とも呼ばれます。

ActiveX コントロールメソッドの詳細については、「 [MFC Activex コントロール: メソッド](mfc-activex-controls-methods.md)」を参照してください。

ActiveX コントロールは、ストックとカスタムの両方のメソッドとプロパティを実装できます。 クラス `COleControl` は、ストックプロパティの実装を提供します。 (ストックプロパティの完全な一覧については、「 [MFC ActiveX コントロール: ストックプロパティの追加](mfc-activex-controls-adding-stock-properties.md)」を参照してください)。開発者によって定義されたカスタムプロパティは、ActiveX コントロールに特殊な機能を追加します。 詳細については、「 [MFC ActiveX コントロール: カスタムプロパティの追加](mfc-activex-controls-adding-custom-properties.md)」を参照してください。

カスタムプロパティとストックプロパティは、メソッドのように、プロパティとメソッド、およびクラスの既存のメンバー関数を処理するディスパッチマップで構成されるメカニズムによってサポートされ `COleControl` ます。 また、これらのプロパティには、開発者が追加情報をコントロールに渡すために使用するパラメーターを含めることができます。

次の記事では、ActiveX コントロールのプロパティについて詳しく説明します。

- [MFC ActiveX コントロール: ストック プロパティの追加](mfc-activex-controls-adding-stock-properties.md)

- [MFC ActiveX コントロール: カスタム プロパティの追加](mfc-activex-controls-adding-custom-properties.md)

- [MFC ActiveX コントロール: 高度なプロパティの実装](mfc-activex-controls-advanced-property-implementation.md)

- [MFC ActiveX コントロール: アンビエント プロパティへのアクセス](mfc-activex-controls-accessing-ambient-properties.md)

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)
