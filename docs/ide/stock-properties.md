---
title: ストック プロパティ | Microsoft Docs
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
ms.openlocfilehash: 4a9b2aa4389d693cfc6734a29f3a744e955ca3ea
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213794"
---
# <a name="stock-properties"></a>ストック プロパティ
[[プロパティ追加ウィザード]](../ide/idl-attributes-add-property-wizard.md) を使用し、MFC ディスパッチ インターフェイスにプロパティを追加する場合、ウィザードの [[名前]](../ide/names-add-property-wizard.md) ページの **[プロパティ名]** 一覧からストック プロパティを選択できます。 選択できるプロパティは次のとおりです。  
  
|プロパティ名|説明|  
|-------------------|-----------------|  
|**外観**|コントロールの外観を決定する値を返すか設定します。 コントロールの **[外観]** プロパティには、3D 表示効果を含めることも省略することもできます。 これはアンビエント読み取り/書き込みプロパティです。|  
|`BackColor`|コントロールのアンビエント `BackColor` プロパティを返すか、パレット (RGB) 色か定義済みのシステム色に設定します。 既定では、その値はコントロールのコンテナーの前景色に一致します。 これはアンビエント読み取り/書き込みプロパティです。|  
|`BorderStyle`|コントロールの境界線スタイルを返すか設定します。 これは読み取り/書き込みプロパティです。|  
|**[キャプション]**|コントロールの **[キャプション]** プロパティを返すか設定します。 このキャプションはウィンドウのタイトルです。 **キャプション**には、**メンバー変数**実装型がありません。|  
|**有効**|コントロールの **[有効]** プロパティを返すか設定します。 有効コントロールは、ユーザー生成イベントに応答できます。|  
|**フォント**|コントロールのアンビエント フォントを返すか設定します。 コントロールにフォントがない場合、Null になります。|  
|`ForeColor`|コントロールのアンビエント `ForeColor` プロパティを返すか設定します。|  
|**hWnd**|コントロールの **[hWnd]** プロパティを返すか設定します。 **hWnd** には、**メンバー変数**実装型がありません。|  
|**ReadyState**|コントロールの **[ReadyState]** プロパティを返すか設定します。 コントロールの状態には、「初期化されていません」、「初期化されています」、「読み込んでいます」、「インタラクティブ」、「完了」があります。 詳細については、*インターネット SDK* の [READYSTATE](https://msdn.microsoft.com/library/aa768362.aspx) に関するページを参照してください。|  
|**[テキスト]**|コントロールに格納されているテキストを返すか設定します。 **テキスト**には、**メンバー変数**実装型がありません。|  
  
## <a name="see-also"></a>参照  
 [プロパティの追加](../ide/adding-a-property-visual-cpp.md)   
 [[IDL 属性] (プロパティの追加ウィザード)](../ide/idl-attributes-add-property-wizard.md)