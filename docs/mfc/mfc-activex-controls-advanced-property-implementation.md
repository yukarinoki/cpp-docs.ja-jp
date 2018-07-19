---
title: 'MFC ActiveX コントロール: プロパティの実装の詳細 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 2eb3ba387d4b6fcca7b30cd360dff84b9da4302a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928365"
---
# <a name="mfc-activex-controls-advanced-property-implementation"></a>MFC ActiveX コントロール : 高度なプロパティの実装
この記事では、ActiveX コントロールのプロパティを高度な実装に関連するトピックについて説明します。  
  
-   [読み取り専用であり、書き込み専用のプロパティ](#_core_read2donly_and_write2donly_properties)  
  
-   [プロパティから返されるエラー コード](#_core_returning_error_codes_from_a_property)  
  
##  <a name="_core_read2donly_and_write2donly_properties"></a> 読み取り専用であり、書き込み専用のプロパティ  
 プロパティの追加ウィザードでは、迅速かつ簡単なコントロールの読み取り専用または書き込み専用のプロパティを実装するメソッドを提供します。  
  
#### <a name="to-implement-a-read-only-or-write-only-property"></a>読み取り専用または書き込み専用プロパティを実装するには  
  
1.  コントロールのプロジェクトを読み込みます。  
  
2.  [クラス ビュー] で、コントロールのライブラリ ノードを展開します。  
  
3.  コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。  
  
4.  ショートカット メニューから **[追加]** をクリックし、**プロパティの追加**です。  
  
     開き、[プロパティの追加ウィザード](../ide/names-add-property-wizard.md)です。  
  
5.  **プロパティ名**ボックス、プロパティの名前を入力します。  
  
6.  **[実装型]** として、 **[Get/Set メソッド]** をクリックします。  
  
7.  **プロパティの型**ボックスで、プロパティの適切な型を選択します。  
  
8.  読み取り専用プロパティを設定する場合は、セット関数名を削除します。 書き込み専用プロパティを設定する場合は、Get 関数名を削除します。  
  
9. **[完了]** をクリックします。  
  
 プロパティの追加ウィザードが、関数を挿入します。 これを行うときに`SetNotSupported`または`GetNotSupported`、ディスパッチ マップ エントリで、通常の代わりに次のように設定します。 または関数を取得します。  
  
 読み取り専用または書き込み専用である既存のプロパティを変更する場合は、ディスパッチ マップを手動で編集し、コントロール クラスから不要な設定または取得関数を削除します。  
  
 読み取り専用または書き込み専用 (たとえば、特定のモードで、コントロールが動作しているときのみ) では条件付きでプロパティを設定する場合は、通常どおり、Set または Get 関数を提供および呼び出し、`SetNotSupported`または`GetNotSupported`適切な場所に機能します。 例えば:  
  
 [!code-cpp[NVC_MFC_AxUI#29](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-property-implementation_1.cpp)]  
  
 このサンプル コードを呼び出す`SetNotSupported`場合、`m_bReadOnlyMode`データ メンバーは**TRUE**です。 場合**FALSE**プロパティは、新しい値に設定されます。  
  
##  <a name="_core_returning_error_codes_from_a_property"></a> プロパティから返されるエラー コード  
 取得またはプロパティを設定しているときにエラーが発生したことを示すために使用して、`COleControl::ThrowError`をパラメーターとして SCODE (状態コード) を受け取る関数。 定義済み SCODE を使用したり、独自のいずれかを定義することができます。 定義済みの SCODEs とカスタム SCODEs を定義するための手順の一覧は、次を参照してください。 [、ActiveX コントロールでのエラーの処理](../mfc/mfc-activex-controls-advanced-topics.md)、アーティクルの ActiveX コントロール: 高度なトピックです。  
  
 ヘルパー関数が存在する最も一般的な SCODEs のように定義済みの[COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported)、 [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported)、および[COleControl::SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).  
  
> [!NOTE]
>  `ThrowError` このプロパティの Get または Set 内のエラーを返すための手段としてのみ使用するものでは関数またはオートメーション メソッドです。 これらは、スタックの適切な例外ハンドラーとなる時間が表示されます。  
  
 他の領域で、コードの例外を報告の詳細については、次を参照してください[COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror)およびセクション[、ActiveX コントロールでのエラーの処理](../mfc/mfc-activex-controls-advanced-topics.md)記事 ActiveX コントロール: 高度な。トピックです。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX コントロール: プロパティ](../mfc/mfc-activex-controls-properties.md)   
 [MFC ActiveX コントロール: メソッド](../mfc/mfc-activex-controls-methods.md)   
 [COleControl クラス](../mfc/reference/colecontrol-class.md)
