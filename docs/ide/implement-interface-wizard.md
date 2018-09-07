---
title: インターフェイス実装ウィザード | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.impl.interface.overview
dev_langs:
- C++
helpviewer_keywords:
- Implement Interface Wizard [C++]
ms.assetid: 947c329e-0815-4ca7-835e-c41dfeb75f9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c43619fcb1d684d7e0d2d6645b7a5feaac61e472
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43195196"
---
# <a name="implement-interface-wizard"></a>インターフェイス実装ウィザード
このウィザードは、COM オブジェクトのインターフェイスを実装します。 Visual Studio と Windows で利用できる COM ライブラリには、多くのインターフェイスの実装が含まれています。 インターフェイスの実装は、オブジェクトのインスタンスの作成時にそのオブジェクトに関連付けられ、オブジェクトで提供されるサービスを提供します。  
  
 インターフェイスと実装の詳細については、Windows SDK の「[Interfaces and Interface Implementations](/windows/desktop/com/interfaces-and-interface-implementations)」 (インターフェイスとインターフェイスの実装) を参照してください。  
  
 **インターフェイスの実装元**  
 インターフェイスの作成元となる、タイプ ライブラリの場所を指定します。  
  
|オプション|説明|  
|------------|-----------------|  
|**プロジェクト**|タイプ ライブラリはプロジェクトの一部です。|  
|**Registry**|タイプ ライブラリはシステムで登録されます。 登録されているタイプ ライブラリは、**[Available type libraries]\(使用可能なタイプ ライブラリ\)** にリストされます。|  
|**ファイル**|タイプ ライブラリは必ずしもシステムで登録されるわけではありませんが、ファイルには含まれます。 ファイルの場所は **[場所]** で指定する必要があります。|  
  
 **[Available type libraries]\(使用可能なタイプ ライブラリ\)**  
 実装できるインターフェイスの定義を含む使用可能なタイプ ライブラリを表示します。 **[インターフェイスの実装元]** の **[ファイル]** をクリックした場合、このボックスは変更できません。  
  
 **場所**  
 **[Available type libraries]\(使用可能なタイプ ライブラリ\)** リストで現在選択されているタイプ ライブラリの場所を表示します。 **[インターフェイスの実装元]** で **[ファイル]** を選択した場合は、省略記号ボタンをクリックして、使用するタイプ ライブラリを含むファイルを見つけます。  
  
 **インターフェイス**  
 **[Available type libraries]\(使用可能なタイプ ライブラリ\)** ボックスで現在選択されているタイプ ライブラリに定義が含まれているインターフェイスを表示します。  
  
> [!NOTE]
>  選択されているオブジェクトで既に実装されているものと同じ名前を持つインターフェイスは、**[インターフェイス]** ボックスには表示されません。  
  
|転送ボタン|説明|  
|---------------------|-----------------|  
|**>**|**[複数のインターフェイスの実装]** リストに、**[インターフェイス]** リストで現在選択されているインターフェイス名を追加します。|  
|**>>**|**[複数のインターフェイスの実装]** リストに、**[インターフェイス]** リストで使用可能なすべてのインターフェイス名を追加します。|  
|**<**|**[複数のインターフェイスの実装]** リストで現在選択されているインターフェイス名を削除します。|  
|**<\<**|**[複数のインターフェイスの実装]** リストに現在リストされているすべてのインターフェイス名を削除します。|  
  
 **複数のインターフェイスの実装**  
 オブジェクトに実装するために選択したインターフェイスの名前を表示します。  
  
> [!NOTE]
>  `IDispatch` から派生する複数のインターフェイスを含める場合や、クラスに既に存在する別のインターフェイスから派生しているインターフェイスの実装を試みる場合は、COM_MAP エントリのあいまいさを解消する必要があります。 詳細については、「[COM_INTERFACE_ENTRY2](../atl/reference/com-interface-entry-macros.md#com_interface_entry2)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [インターフェイスの実装](../ide/implementing-an-interface-visual-cpp.md)