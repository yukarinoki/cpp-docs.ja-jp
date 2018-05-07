---
title: 永続化と初期化の最適化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], optimizing
- performance, ActiveX controls
- optimization, ActiveX controls
- optimizing performance, ActiveX controls
ms.assetid: e821e19e-b9eb-49ab-b719-0743420ba80b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e528ea7901518112c255eefbfb1e674fddee04e2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="optimizing-persistence-and-initialization"></a>永続化と初期化の最適化
既定では、によって永続化とコントロールの初期化を処理します。、`DoPropExchange`メンバー関数。 この関数がいくつかの呼び出しを含む、一般的なコントロール**px _** 関数 (`PX_Color`、`PX_Font`など) の各プロパティのいずれか。  
  
 このアプローチには、利用する、1 つ`DoPropExchange`初期化、バイナリ形式で永続化および永続化では、いくつかのコンテナーで使用される、いわゆる「プロパティ バッグ」形式の実装を使用できます。 この 1 つの関数は、プロパティと 1 つの場所では、その既定値に関するすべての情報を提供します。  
  
 ただし、この効率は低下します。 **Px _** 関数取得本質的には、重層的な実装を通じて機能には柔軟性がより直接的が低く柔軟性の高い方法よりも効率的です。 さらに、コントロールが既定値を渡す場合、 **px _** 関数は、既定値にする必要があります、既定値は必ずしもを使用できない場合であっても、毎回が提供されることです。 場合、既定値を生成する、複雑なタスク (たとえば、値がアンビエント プロパティから取得したとき)、余分な既定値が使用されていない場合に不要な処理が行われます。  
  
 コントロールのオーバーライドすることで、コントロールのバイナリの永続化のパフォーマンスを向上できる`Serialize`関数。 このメンバー関数の既定の実装への呼び出し、`DoPropExchange`関数。 これをオーバーライドすることで、バイナリの永続化のためより直接的な実装を提供できます。 たとえば、この`DoPropExchange`関数。  
  
 [!code-cpp[NVC_MFC_AxOpt#1](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_1.cpp)]  
  
 このコントロールのバイナリの永続化のパフォーマンスを向上させるには、オーバーライド、`Serialize`次のように機能します。  
  
 [!code-cpp[NVC_MFC_AxOpt#2](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_2.cpp)]  
  
 `dwVersion`ローカル変数は、バージョン コントロールの永続的な状態の読み込みまたは保存を検出するために使用することができます。 この変数を使用するには呼び出す代わりに[CPropExchange::GetVersion](../mfc/reference/cpropexchange-class.md#getversion)です。  
  
 永続的な形式で、小さい領域を保存する、 **BOOL**プロパティ (、によって生成される形式との互換性を保つ`PX_Bool`)、としてプロパティを格納することができます、**バイト**、次のようにします。  
  
 [!code-cpp[NVC_MFC_AxOpt#3](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_3.cpp)]  
  
 キャストするのではなく、負荷の場合、一時変数を使用するとし、その値が割り当てられます、`m_boolProp`を**バイト**参照します。 キャスト手法の 1 バイトだけになる`m_boolProp`変更される、初期化されていない残りのバイトします。  
  
 同じコントロールは、オーバーライドすることで、コントロールの初期化を最適化できます[COleControl::OnResetState](../mfc/reference/colecontrol-class.md#onresetstate)次のようにします。  
  
 [!code-cpp[NVC_MFC_AxOpt#4](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_4.cpp)]  
  
 `Serialize`と`OnResetState`オーバーライドされている、`DoPropExchange`関数を保持するかそのままのプロパティ バッグ形式で永続化に使用されているためです。 これが、コンテナーのメカニズムを使用する永続化に関係なくのコントロールがそのプロパティを一貫した管理することを確認するこれらの関数の 3 つすべてを維持するために重要です。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール: 最適化](../mfc/mfc-activex-controls-optimization.md)

