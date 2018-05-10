---
title: IDL 属性、プロパティの追加ウィザード |Microsoft ドキュメント
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
ms.openlocfilehash: 77931296d8d33337c4e630b7327a1ec8fd0a458f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="idl-attributes-add-property-wizard"></a>[IDL 属性] (プロパティの追加ウィザード)
プロパティの追加ウィザードのこのページを使用すると、プロパティの任意のインターフェイス定義言語 (IDL) の設定を指定できます。  
  
 **ID**  
 プロパティを識別する数値 ID を設定します。 このオプションでは、カスタム インターフェイスのプロパティを使用できません。 参照してください[id](http://msdn.microsoft.com/library/windows/desktop/aa367040)で、 *MIDL 参照*です。  
  
 **helpcontext**  
 コンテキスト ID をユーザーに関する情報を表示、ヘルプ ファイルでこのプロパティを指定します。 参照してください[helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851)で、 *MIDL 参照*です。  
  
 **helpstring**  
 適用すると、要素の記述に使用される文字の文字列を指定します。 既定では、その設定が"プロパティ*プロパティ名*"。 参照してください[helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856)で、 *MIDL 参照*です。  
  
## <a name="other-options"></a>その他のオプション  
 すべてのオプションすべてのプロパティ タイプを利用できます。  
  
|オプション|説明|  
|------------|-----------------|  
|**bindable**|プロパティがデータ バインディングをサポートしていることを示します。 参照してください[バインド可能な](http://msdn.microsoft.com/library/windows/desktop/aa366738)で、 *MIDL 参照*です。 プロパティのストックの実装には、このオプションは、既定で設定され、変更不可能なです。|  
|**defaultbind**|このベスト、単一のバインド可能なプロパティを表すことを示すオブジェクト。 参照してください[defaultbind](http://msdn.microsoft.com/library/windows/desktop/aa366790)で、 *MIDL 参照*です。|  
|**displaybind**|このプロパティをバインド可能なとしてユーザーに表示することを示します。 参照してください[displaybind](http://msdn.microsoft.com/library/windows/desktop/aa366804)で、 *MIDL 参照*です。|  
|**immediatebind**|データ バインドされたオブジェクトのプロパティに対する変更をすべてのデータベースに直ちに通知されることを示します。 参照してください[immediatebind](http://msdn.microsoft.com/library/windows/desktop/aa367045)で、 *MIDL 参照*です。|  
|**defaultcollelem**|プロパティが既定のコレクションの要素のアクセサー関数であることを示します。 参照してください[defaultcollelem](http://msdn.microsoft.com/library/windows/desktop/aa366792)で、 *MIDL 参照*です。|  
|**nonbrowsable**|タグでインターフェイスまたはディスパッチ インターフェイスのメンバーは、プロパティ ブラウザーでは表示されません。 参照してください[nonbrowsable](http://msdn.microsoft.com/library/windows/desktop/aa367117)で、 *MIDL 参照*です。|  
|**requestedit**|プロパティをサポートしていることを示します、 **OnRequestEdit**通知を参照してください[requestedit](http://msdn.microsoft.com/library/windows/desktop/aa367155)で、 *MIDL 参照*です。 プロパティのストックの実装には、このオプションは、既定で設定され、変更不可能なです。|  
|**ソース**|プロパティのメンバーは、イベントの発生元であることを示します。 参照してください[ソース](http://msdn.microsoft.com/library/windows/desktop/aa367166)で、 *MIDL 参照*です。|  
|**hidden**|プロパティが存在するが、ユーザー指向ブラウザーに表示されます必要がありますいないことを示します。 参照してください[隠し](http://msdn.microsoft.com/library/windows/desktop/aa366861)で、 *MIDL 参照*です。|  
|**restricted**|プロパティを任意に呼び出すことができませんを指定します。 参照してください[制限](http://msdn.microsoft.com/library/windows/desktop/aa367157)で、 *MIDL 参照*です。|  
|`local`|MIDL コンパイラにプロパティがリモートでないことを指定します。 参照してください[ローカル](http://msdn.microsoft.com/library/windows/desktop/aa367071)で、 *MIDL 参照*です。|  
  
## <a name="see-also"></a>関連項目  
 [プロパティを追加します。](../ide/adding-a-property-visual-cpp.md)   
 [名前、プロパティの追加ウィザード](../ide/names-add-property-wizard.md)   
 [インターフェイスを実装します。](../ide/implementing-an-interface-visual-cpp.md)   
 [ストック プロパティ](../ide/stock-properties.md)