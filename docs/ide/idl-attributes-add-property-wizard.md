---
title: '[IDL 属性] (プロパティの追加ウィザード) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.prop.idlattributes
dev_langs:
- C++
ms.assetid: 356ed666-79d0-4bd9-a5e7-cda679cbadbd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 12fee7eadecbd81e3c4e410d254de50bcf3a9ac0
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208827"
---
# <a name="idl-attributes-add-property-wizard"></a>[IDL 属性] (プロパティの追加ウィザード)
プロパティの追加ウィザードのこのページでは、プロパティのインターフェイス定義言語 (IDL) の設定を指定します。  
  
 **ID**  
 プロパティを識別する数値 ID を設定します。 このオプションは、カスタム インターフェイスのプロパティでは使用できません。 *MIDL リファレンス*の [id](/windows/desktop/Midl/id) に関するページを参照してください。  
  
 **helpcontext**  
 コンテキスト ID を指定します。ユーザーはヘルプ ファイルでこのプロパティに関する情報を参照できます。 *MIDL リファレンス*の [helpcontext](/windows/desktop/Midl/helpcontext) に関するページを参照してください。  
  
 **helpstring**  
 適用先となる要素を記述するために使用される文字列を指定します。 既定では、"プロパティ <*プロパティ名*>" に設定されます。 *MIDL リファレンス*の [helpstring](/windows/desktop/Midl/helpstring) に関するページを参照してください。  
  
## <a name="other-options"></a>その他のオプション  
 すべてのオプションをすべてのプロパティの種類で使用できるわけではありません。  
  
|オプション|説明|  
|------------|-----------------|  
|**bindable**|プロパティがデータ バインディングをサポートすることを示します。 *MIDL リファレンス*の [bindable](/windows/desktop/Midl/bindable) に関するページを参照してください。 プロパティのストック実装では、このオプションは既定で設定され、変更できません。|  
|**defaultbind**|これがオブジェクトを最もよく表す 1 つのバインド可能なプロパティであることを示します。 *MIDL リファレンス*の [defaultbind](/windows/desktop/Midl/defaultbind) に関するページを参照してください。|  
|**displaybind**|このプロパティをユーザーにバインド可能として表示する必要があることを示します。 *MIDL リファレンス*の [displaybind](/windows/desktop/Midl/displaybind) に関するページを参照してください。|  
|**immediatebind**|データ バインディング オブジェクトのこのプロパティに対するすべての変更が、すぐにデータベースに通知されることを示します。 *MIDL リファレンス*の [immediatebind](/windows/desktop/Midl/immediatebind) に関するページを参照してください。|  
|**defaultcollelem**|プロパティが既定コレクションの要素に対するアクセサー関数であることを示します。 *MIDL リファレンス*の [defaultcollelem](/windows/desktop/Midl/defaultcollelem) に関するページを参照してください。|  
|**nonbrowsable**|プロパティ ブラウザーに表示してはならない interface または dispinterface メンバーにタグを付けます。 *MIDL リファレンス*の [nonbrowsable](/windows/desktop/Midl/nonbrowsable) に関するページを参照してください。|  
|**requestedit**|プロパティが **OnRequestEdit** 通知をサポートすることを示します。*MIDL リファレンス*の [requestedit](/windows/desktop/Midl/requestedit) に関するページを参照してください。 プロパティのストック実装では、このオプションは既定で設定され、変更できません。|  
|**source**|プロパティのメンバーがイベントのソースであることを示します。 *MIDL リファレンス* の [source](/windows/desktop/Midl/source) に関するページを参照してください。|  
|**hidden**|プロパティは存在しますが、ユーザー指向ブラウザーでは表示されないことを示します。 *MIDL リファレンス*の [hidden](/windows/desktop/Midl/hidden) に関するページを参照してください。|  
|**restricted**|プロパティを任意に呼び出せないことを指定します。 *MIDL リファレンス* の [restricted](/windows/desktop/Midl/restricted) に関するページを参照してください。|  
|`local`|プロパティがリモートでないことを MIDL コンパイラに対して指定します。 *MIDL リファレンス* の [local](/windows/desktop/Midl/local) に関するページを参照してください。|  
  
## <a name="see-also"></a>参照  
 [プロパティの追加](../ide/adding-a-property-visual-cpp.md)   
 [[名前] (プロパティの追加ウィザード)](../ide/names-add-property-wizard.md)   
 [インターフェイスの実装](../ide/implementing-an-interface-visual-cpp.md)   
 [ストック プロパティ](../ide/stock-properties.md)