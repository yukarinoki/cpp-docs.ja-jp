---
title: 'MFC ActiveX コントロール: プロパティの実装の詳細 |Microsoft Docs'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
ms.assetid: ec2e6759-5a8e-41d8-a275-99af8ff6f32e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e5357354a747dd2ce2487bf66821e8be7d2a04a4
ms.sourcegitcommit: b4432d30f255f0cb58dce69cbc8cbcb9d44bc68b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "45534925"
---
# <a name="mfc-activex-controls-advanced-property-implementation"></a>MFC ActiveX コントロール : 高度なプロパティの実装
この記事では、ActiveX コントロールのプロパティを高度な実装に関連するトピックについて説明します。

>[!IMPORTANT]
> ActiveX は、新規の開発が使用できないレガシ テクノロジです。 ActiveX の上書きの最新のテクノロジの詳細については、次を参照してください。 [ActiveX コントロール](activex-controls.md)します。  
  
-   [読み取り専用であり、書き込み専用のプロパティ](#_core_read2donly_and_write2donly_properties)  
  
-   [プロパティから返されるエラー コード](#_core_returning_error_codes_from_a_property)  
  
##  <a name="_core_read2donly_and_write2donly_properties"></a> 読み取り専用であり、書き込み専用のプロパティ  
 プロパティの追加ウィザードでは、コントロールの読み取り専用または書き込み専用のプロパティを実装するために素早く簡単にメソッドを提供します。  
  
#### <a name="to-implement-a-read-only-or-write-only-property"></a>読み取り専用または書き込み専用プロパティを実装するには  
  
1.  コントロールのプロジェクトを読み込みます。  
  
2.  [クラス ビュー] で、コントロールのライブラリ ノードを展開します。  
  
3.  コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。  
  
4.  ショートカット メニューでは、次のようにクリックします。**追加** をクリックし、**プロパティの追加**します。  
  
     開き、[プロパティの追加ウィザード](../ide/names-add-property-wizard.md)します。  
  
5.  **プロパティ名**ボックス、プロパティの名前を入力します。  
  
6.  **[実装型]** として、 **[Get/Set メソッド]** をクリックします。  
  
7.  **プロパティ型**ボックスで、プロパティの適切な型を選択します。  
  
8.  読み取り専用プロパティを設定する場合は、セット関数名を削除します。 書き込み専用プロパティを設定する場合は、Get 関数名を削除します。  
  
9. **[完了]** をクリックします。  
  
 プロパティの追加ウィザードが、関数を挿入するときに、これを行うと、`SetNotSupported`または`GetNotSupported`通常の代わりにディスパッチ マップ エントリの次のように設定します。 または関数を取得します。  
  
 読み取り専用または書き込み専用にする既存のプロパティを変更する場合は、ディスパッチ マップを手動で編集し、コントロール クラスから不要な設定または取得関数を削除します。  
  
 プロパティを読み取り専用または書き込み専用 (たとえば、コントロールが特定のモードで動作している場合のみ) では条件付きでを実行する場合に、通常どおり、Set または Get 関数を提供および呼び出し、`SetNotSupported`または`GetNotSupported`適切な場所に機能します。 例えば:  
  
 [!code-cpp[NVC_MFC_AxUI#29](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-property-implementation_1.cpp)]  
  
 このサンプル コードを呼び出す`SetNotSupported`場合、`m_bReadOnlyMode`データ メンバーが**TRUE**します。 場合**FALSE**プロパティが新しい値に設定されます。  
  
##  <a name="_core_returning_error_codes_from_a_property"></a> プロパティから返されるエラー コード  
 プロパティを取得または設定しようとしています。 中にエラーが発生したことを示す、を使用して、`COleControl::ThrowError`関数は、パラメーターとして SCODE (状態コード) をとります。 定義済み SCODE を使用したり、独自のいずれかを定義することができます。 定義済みの SCODEs とカスタム SCODEs を定義するための手順の一覧は、次を参照してください。 [、ActiveX コントロールでのエラーの処理](../mfc/mfc-activex-controls-advanced-topics.md)、記事の ActiveX コントロール: 高度なトピックです。  
  
 定義済み SCODEs などを最も一般的なのヘルパー関数が存在[COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported)、 [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported)、および[COleControl::SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).  
  
> [!NOTE]
>  `ThrowError` プロパティの Get または Set 内からのエラーを返すための手段としてのみ使用するものでは関数またはオートメーション メソッド。 これらは、唯一のスタックの適切な例外ハンドラーとなる時間を表示します。  
  
 コードの他の領域で例外をレポートの詳細については、次を参照してください[COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) 」、および[エラーを処理する、ActiveX コントロールで](../mfc/mfc-activex-controls-advanced-topics.md)で ActiveX コントロール: 高度な。トピックを示します。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX コントロール: プロパティ](../mfc/mfc-activex-controls-properties.md)   
 [MFC ActiveX コントロール: メソッド](../mfc/mfc-activex-controls-methods.md)   
 [COleControl クラス](../mfc/reference/colecontrol-class.md)
