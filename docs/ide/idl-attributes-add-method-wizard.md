---
title: IDL 属性、メソッド追加ウィザード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.method.idlattrib
dev_langs:
- C++
helpviewer_keywords:
- Add Method Wizard [C++]
- IDL attributes, Add Method Wizard
ms.assetid: f80c3bc1-b515-4d6c-83ee-98c2c21ba902
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a7a1e8fe89f64ad5909e7c1415545e3b3d80196
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="idl-attributes-add-method-wizard"></a>IDL 属性、メソッド追加ウィザード
メソッド追加ウィザードのこのページを使用すると、メソッドの任意のインターフェイス定義言語 (IDL) の設定を指定できます。  
  
 **ID**  
 メソッドを識別する数値 ID を設定します。 参照してください[id](http://msdn.microsoft.com/library/windows/desktop/aa367040)で、 *MIDL 参照*です。  
  
 このボックスは、カスタム インターフェイスでは使用できません、MFC ディスパッチ インターフェイスでは使用できません。  
  
 **call_as**  
 このローカル メソッドをマップできるリモート メソッドの名前を指定します。 参照してください[call_as](http://msdn.microsoft.com/library/windows/desktop/aa366748)で、 *MIDL 参照*です。  
  
 MFC ディスパッチ インターフェイスは使用できません。  
  
 **helpcontext**  
 コンテキスト ID をユーザーに関する情報を表示、ヘルプ ファイルでこのメソッドを指定します。 参照してください[helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851)で、 *MIDL 参照*です。  
  
 MFC ディスパッチ インターフェイスは使用できません。  
  
 **helpstring**  
 適用すると、要素の記述に使用される文字の文字列を指定します。 既定では、その設定は"メソッド*メソッド名*"。 参照してください[helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856)で、 *MIDL 参照*です。  
  
 MFC ディスパッチ インターフェイスは使用できません。  
  
 **追加の属性**  
 MFC ディスパッチ インターフェイスは使用できません。  
  
|属性|説明|  
|---------------|-----------------|  
|**hidden**|メソッドが存在するが、ユーザー指向ブラウザーに表示されます必要がありますいないことを示します。 参照してください[隠し](http://msdn.microsoft.com/library/windows/desktop/aa366861)で、 *MIDL 参照*です。|  
|**ソース**|メソッドのメンバーは、イベントの発生元であることを示します。 参照してください[ソース](http://msdn.microsoft.com/library/windows/desktop/aa367166)で、 *MIDL 参照*です。|  
|`local`|MIDL コンパイラにメソッドがリモートでないことを指定します。 参照してください[ローカル](http://msdn.microsoft.com/library/windows/desktop/aa367071)で、 *MIDL 参照*です。|  
|**restricted**|メソッドを任意に呼び出すことができませんを指定します。 参照してください[制限](http://msdn.microsoft.com/library/windows/desktop/aa367157)で、 *MIDL 参照*です。|  
|**vararg**|メソッドが可変個の引数を取ることを指定します。 これを実現する最後の引数がありますのセーフ配列**バリアント**を残りのすべての引数を含む型。 参照してください[vararg](http://msdn.microsoft.com/library/windows/desktop/aa367304)で、 *MIDL 参照*です。|  
  
## <a name="see-also"></a>関連項目  
 [メソッドの追加](../ide/adding-a-method-visual-cpp.md)   
 [メソッド追加ウィザード](../ide/add-method-wizard.md)