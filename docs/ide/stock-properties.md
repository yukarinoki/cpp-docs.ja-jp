---
title: ストック プロパティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- stock properties, about stock properties
- stock properties
ms.assetid: a89fc454-0b8e-447a-9033-4c8af46a24d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3586fb33c30148c870b096d0d49a41d7ad8c6c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="stock-properties"></a>ストック プロパティ
MFC ディスパッチ インターフェイスを使用して、プロパティを追加しているかどうか、[プロパティの追加ウィザード](../ide/idl-attributes-add-property-wizard.md)からのストック プロパティを選択することができます、**プロパティ名**一覧に、[名](../ide/names-add-property-wizard.md)のページ、ウィザード。 選択できるプロパティは次のとおりです。  
  
|プロパティ名|説明|  
|-------------------|-----------------|  
|**外観**|返します。 または、コントロールの外観を決定する値を設定します。 コントロールの**外観**プロパティが含まれますまたは 3 次元表示効果を省略します。 これは、アンビエント読み取り/書き込みプロパティです。|  
|`BackColor`|返すか、コントロールのアンビエント設定`BackColor`パレット (RGB) の色または定義済みのシステム カラーのいずれかのプロパティです。 既定では、その値は、コントロールのコンテナーの前景色に対応します。 これは、アンビエント読み取り/書き込みプロパティです。|  
|`BorderStyle`|返します。 または、コントロールの境界線スタイルを設定します。 これは、読み取り/書き込みプロパティです。|  
|**[キャプション]**|コントロールの設定を取得または**キャプション**プロパティです。 キャプションは、ウィンドウのタイトルです。 **キャプション**持たない**メンバー変数**実装の型。|  
|**有効**|コントロールの設定を取得または**有効**プロパティです。 有効なコントロールは、ユーザーが生成したイベントに応答できます。|  
|**フォント**|返します。 または、コントロールのアンビエント フォントを設定します。 コントロールにフォントがあるない場合は null です。|  
|`ForeColor`|返すか、コントロールのアンビエント設定`ForeColor`プロパティです。|  
|**hWnd**|コントロールの設定を取得または**hWnd**プロパティです。 **hWnd**持たない**メンバー変数**実装の型。|  
|**ReadyState**|コントロールの設定を取得または**ReadyState**プロパティです。 コントロールは、初期化されていない、初期化、読み込み、対話型、または完了できます。 参照してください[READYSTATE](https://msdn.microsoft.com/en-us/library/aa768362.aspx)で、*インターネット SDK*詳細についてはします。|  
|**[テキスト]**|返します。 または、コントロール内のテキストを設定します。 **テキスト**持たない**メンバー変数**実装の型。|  
  
## <a name="see-also"></a>関連項目  
 [プロパティを追加します。](../ide/adding-a-property-visual-cpp.md)   
 [[IDL 属性] (プロパティの追加ウィザード)](../ide/idl-attributes-add-property-wizard.md)