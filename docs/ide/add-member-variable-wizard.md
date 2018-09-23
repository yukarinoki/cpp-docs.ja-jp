---
title: メンバー変数の追加ウィザード | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.variable.overview
dev_langs:
- C++
helpviewer_keywords:
- Add Member Variable Wizard [C++]
ms.assetid: 73e8fa99-ac1a-42e2-8fc2-4684b9eb6d4d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4d4518a48d51e6187015dc3fd7b5456e04e1ae84
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701533"
---
# <a name="add-member-variable-wizard"></a>メンバー変数の追加ウィザード
このウィザードは、ヘッダー ファイルにメンバー変数宣言を追加し、オプションに応じてコードを .cpp ファイルに追加できます。 このウィザードを使用してメンバー変数を追加すると、開発環境でそのコードを編集できます。  
  
- **アクセス**

   メンバー変数へのアクセス権を設定します。 アクセス修飾子とは、メンバー変数に対して他のクラスが持つアクセス権を指定するキーワードです。 アクセス権の指定の詳細については、「[メンバー アクセス コントロール](../cpp/member-access-control-cpp.md)」を参照してください。 メンバー変数のアクセス レベルの既定の設定は、**public** です。  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../cpp/protected-cpp.md)  
  
-   [private](../cpp/private-cpp.md)  
  
- **変数の型**

   追加するメンバー変数の戻り値の型を設定します。  
  
   - ダイアログ ボックス コントロールではないメンバー変数を追加する場合は、利用可能な型のリストから選択します。  
  
      戻り値の型については、「[基本型](../cpp/fundamental-types-cpp.md)」を参照してください。  
  
      |||  
      |-|-|  
      |**char**|**short**|  
      |**double**|**unsigned char**|  
      |**float**|**unsigned int**|  
      |**int**|**unsigned long**|  
      |**long**||  
  
   - ダイアログ ボックス コントロールのメンバー変数を追加する場合、このボックスは、コントロールまたは値に対して返されるオブジェクトの型が入力されます。 **[コントロール]** を選択した場合、**[変数の型]** により **[コントロール ID]** ボックスで選択したコントロールの基底クラスが指定されます。 ダイアログ ボックス コントロールに値を格納することができ、**[値]** を選択した場合、**[変数の型]** によってコントロールに格納できる値の適切な型が指定されます。 詳細については、「[Dialog Box Controls and Variable Types](../ide/dialog-box-controls-and-variable-types.md)」 (ダイアログ ボックス コントロールおよび変数の型) を参照してください。  
  
      この値は、**[コントロール ID]** の選択内容によって異なり、変更はできません。  
  
- **変数名**

   追加するメンバー変数の名前を設定します。 メンバー変数は、通常、既定で提供されている識別用文字列 "m_," で始まります。  
  
- **Control variable (コントロール変数)**

   メンバー変数が、[データ交換とデータの検証](../mfc/dialog-data-exchange-and-validation.md)をサポートしているダイアログ ボックス内のコントロールを管理することを示します。 詳細については、[DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) に関するセクションを参照してください。 このオプションは、[CDialog](../mfc/reference/cdialog-class.md) から派生したクラスに追加されたメンバー変数に対してのみ使用可能です。 **[コントロール ID]** と **[コントロール型]** オプションをアクティブ化するには、このボックスを選択します。  
  
- **コントロール ID**

   追加するコントロール変数の ID を設定します。 メンバー変数を追加するコントロールの型の ID をリストから選択します。 リストは、**[コントロール変数]** ボックスが選択されている場合にのみアクティブで、ダイアログ ボックスに既に追加されたコントロールの ID に制限されます。 たとえば、標準的な **[OK]** ボタンの場合、コントロール ID は **IDOK** です。  
  
   |オプション|説明|  
   |------------|-----------------|  
   |**コントロール**|このオプションは、既定でコントロール型に設定されます。 これはコントロールの状態やコンテンツではなく (リスト ボックス、コンボ ボックス、または編集ボックスで行えるため)、コントロール自体を管理します。|  
   |**[値]**|このオプションは、値を格納できる (編集ボックスなど) または状態を反映できる (チェック ボックスなど) コントロールの型にのみ使用でき、範囲、コンテンツ、または状態を管理することができます。 詳細については、「[Dialog Box Controls and Variable Types](../ide/dialog-box-controls-and-variable-types.md)」 (ダイアログ ボックス コントロールおよび変数の型) を参照してください。|  
  
- **カテゴリ**

   変数の基となるのが、コントロールの種類とコントロール値のどちらであるかを指定します。  
  
- **コントロール型**

   追加するコントロールの型を設定します。 このボックスは、変更できません。 たとえば、ボタンは **BUTTON** というコントロール型を持ち、コンボ ボックスは **COMBOBOX** というコントロール型を持ちます。 詳細については、「[Dialog Box Controls and Variable Types](../ide/dialog-box-controls-and-variable-types.md)」 (ダイアログ ボックス コントロールおよび変数の型) を参照してください。  
  
- **最大文字数**

   **[変数の型]** が [[CString]](../atl-mfc-shared/reference/cstringt-class.md) に設定されている場合にのみ使用できます。 コントロールで保持できる文字の最大数を示します。  
  
- **最小値**

   変数型が **BOOL**、`int`、**UINT**、**long**、`DWORD`、**float**、**double**、**BYTE**、**short**、[COLECurrency](../mfc/reference/colecurrency-class.md)、[CTime](../atl-mfc-shared/reference/ctime-class.md) のいずれかの場合にのみ使用できます。 スケールまたは日付の範囲に許容される最小値を示します。  
  
- **最大値**

   変数型が **BOOL**、`int`、**UINT**、**long**、`DWORD`、**float**、**double**、**BYTE**、**short**、`COLECurrency`、`CTime` のいずれかの場合にのみ使用できます。 スケールまたは日付の範囲に許容される最大値を示します。  
  
- **.h ファイル**

   ActiveX コントロール場合、そのメンバー変数にはラッパー クラスが必要です。 ヘッダー ファイルの名前を設定し、クラス宣言を追加します。  
  
- **.cpp ファイル**

   ActiveX コントロール場合、そのメンバー変数にはラッパー クラスが必要です。 実装ファイルの名前を設定し、クラス定義を追加します。  
  
- **コメント**

   メンバー変数のヘッダー ファイルにコメントを挿入します。  
  
## <a name="see-also"></a>参照  
 [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)