---
title: メンバー変数のウィザードの追加 |Microsoft ドキュメント
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
ms.openlocfilehash: f3ae6a3aef4bdf774b5630a9bb0b2a0b49f7f29b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="add-member-variable-wizard"></a>メンバー変数の追加ウィザード
このウィザードは、ヘッダー ファイルに、メンバー変数宣言を追加し、オプションに応じて、.cpp ファイルにコードを追加します。 ウィザードを使用して、メンバー変数を追加した後は、開発環境でコードを編集することができます。  
  
 **アクセス**  
 メンバー変数へのアクセスを設定します。 アクセス修飾子は、他のクラス メンバー変数へのアクセスを指定するキーワードです。 参照してください[メンバー アクセス コントロール](../cpp/member-access-control-cpp.md)詳細については、アクセスを指定します。 メンバー変数へのアクセス レベルに設定**パブリック**既定です。  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../cpp/protected-cpp.md)  
  
-   [private](../cpp/private-cpp.md)  
  
 **変数の型**  
 戻り値の型を追加するメンバー変数を設定します。  
  
-   ダイアログ ボックス コントロールではないメンバー変数を追加する場合は、利用可能な種類の一覧から選択します。  
  
     型については、次を参照してください。[基本的な型](../cpp/fundamental-types-cpp.md)です。  
  
    |||  
    |-|-|  
    |`char`|**short**|  
    |**double**|`unsigned char`|  
    |**float**|`unsigned int`|  
    |`int`|`unsigned long`|  
    |**long**||  
  
-   ダイアログ ボックス コントロールのメンバー変数を追加する場合、このボックスは、コントロールまたは値に対して返されるオブジェクトの種類が入力されます。 選択した場合**コントロール**、し**変数の型**で選択したコントロールの基底クラスを指定、**コントロール ID**ボックス。 ダイアログ ボックス コントロールは、値を含めることができ、選択した場合**値**、し**変数型**適切なコントロールを含めることができる値の種類を指定します。 参照してください[ダイアログ ボックス コントロールおよび変数の型](../ide/dialog-box-controls-and-variable-types.md)詳細についてはします。  
  
     この値は、選択内容によって異なります。**コントロール ID**は変更できません。  
  
 **変数名**  
 追加するメンバー変数の名前を設定します。 メンバー変数は、通常、識別用文字列「m _」、"を既定で提供されているで始まります。  
  
 **コントロール変数**  
 メンバー変数が、ダイアログ ボックス内のコントロールを管理することを示します[データ交換とデータの検証](../mfc/dialog-data-exchange-and-validation.md)をサポートします。 参照してください[DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)詳細についてはします。 このオプションはから派生したクラスに追加されたメンバー変数に対してのみ使用可能な[CDialog](../mfc/reference/cdialog-class.md)です。 アクティブ化するには、このボックスをオン、**コントロール ID**と**コントロール型**オプション。  
  
 **コントロール ID**  
 追加するコントロール変数の ID を設定します。 メンバー変数を追加するコントロールの種類の ID を一覧から選択します。 一覧は、アクティブな場合にのみ、**制御変数**ボックスが選択されているし、ダイアログ ボックスに既に追加されたコントロールの Id に制限されます。 たとえば、標準的な**OK**ボタン、コントロールの ID は**IDOK**です。  
  
|オプション|説明|  
|------------|-----------------|  
|**コントロール**|このオプションは、コントロール型の既定で設定されます。 (リスト ボックス、コンボ ボックス、または編集ボックスに実行する可能性があります)、コントロール自体の状態やではなく内容を管理するコントロールのです。|  
|**[値]**|このオプションは、(エディット ボックスなどの値を格納したり、(チェック ボックスなど)、状態を反映できるコントロールの種類に対してのみとする利用可能な範囲、内容、または状態を管理することができます。 参照してください[ダイアログ ボックス コントロールおよび変数の型](../ide/dialog-box-controls-and-variable-types.md)詳細についてはします。|  
  
 **カテゴリ**  
 コントロールの種類またはコントロールの値に変数がに基づいて表示するかどうかを指定します。  
  
 **コントロール型**  
 追加するコントロールの種類を設定します。 このボックスは、変更はできません。 たとえば、ボタンには、コントロール型**ボタン**、コンボ ボックスには、コントロール型と**COMBOBOX**です。 参照してください[ダイアログ ボックス コントロールおよび変数の型](../ide/dialog-box-controls-and-variable-types.md)詳細についてはします。  
  
 **最大文字数**  
 場合にのみ使用**変数型**に設定されている[CString](../atl-mfc-shared/reference/cstringt-class.md)です。 コントロールを保持できる文字の最大数を示します。  
  
 **最小値**  
 変数の型が存在する場合のみ**BOOL**、 `int`、 **UINT**、**長い**、 `DWORD`、 **float**、 **二重**、**バイト**、**短い**、 [COLECurrency](../mfc/reference/colecurrency-class.md)または[CTime](../atl-mfc-shared/reference/ctime-class.md)です。 数値または日付の範囲に許容される最小値を示します。  
  
 **最大値**  
 変数の型が存在する場合のみ**BOOL**、 `int`、 **UINT**、**長い**、 `DWORD`、 **float**、 **二重**、**バイト**、**短い**、`COLECurrency`または`CTime`です。 数値または日付の範囲に許容される最大値を示します。  
  
 **.h ファイル**  
 ActiveX コントロールのメンバー変数はラッパー クラスが必要です。 クラス宣言を追加するヘッダー ファイルの名前を設定します。  
  
 **.cpp ファイル**  
 ActiveX コントロールのメンバー変数はラッパー クラスが必要です。 クラス定義を追加する実装ファイルの名前を設定します。  
  
 **コメント**  
 メンバー変数のヘッダー ファイル内のコメントを提供します。  
  
## <a name="see-also"></a>関連項目  
 [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)