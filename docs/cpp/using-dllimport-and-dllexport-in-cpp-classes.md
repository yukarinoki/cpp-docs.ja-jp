---
title: C++ クラスでの dllimport と dllexport の使用 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exporting classes [C++]
- declarations [C++], class
- exportable classes [C++]
- classes [C++], declaring
- classes [C++], exportable and inheritance
- inheritance [C++], exportable classes [C++]
- dllimport attribute [C++], classes
- declaring classes [C++]
- dllexport attribute [C++]
- dllexport attribute [C++], classes [C++]
ms.assetid: 8d7d1303-b9e9-47ca-96cc-67bf444a08a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c7768558b735644a8f98a9380a509098c62dfeb
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943946"
---
# <a name="using-dllimport-and-dllexport-in-c-classes"></a>C++ クラスでの dllimport と dllexport の使用
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 C++ クラスを宣言することができます、 **dllimport**または**dllexport**属性。 これらの形式は、クラス全体がインポートまたはエクスポートされることを暗黙的に指定します。 この方法でエクスポートされたクラスは、エクスポート可能なクラスと呼ばれます。  
  
 次の例では、エクスポート可能なクラスを定義しています。 そのメンバー関数と静的データはすべてエクスポートされます。  
  
```cpp 
#define DllExport   __declspec( dllexport )  
  
class DllExport C {  
   int i;  
   virtual int func( void ) { return 1; }  
};  
```  
  
 その明示的な使用に注意してください、 **dllimport**と**dllexport**エクスポート可能なクラスのメンバーの属性が禁止されています。  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bdllexportclasses"></a> dllexport クラス  
 クラスを宣言するときに**dllexport**、すべてのメンバー関数と静的データ メンバーがエクスポートされます。 このようなすべてのメンバーは同じプログラム内で定義する必要があります。 定義しない場合は、リンカー エラーが生成されます。 この規則の例外は純粋仮想関数です。純粋仮想関数にはこのような明示的な定義は不要です。 ただし、抽象クラスのデストラクターは基底クラスのデストラクターによって常に呼び出されるため、純粋仮想デストラクターには常に明示的な定義が必要です。 これらの規則はエクスポート不可クラスに対しても同じであることに注意してください。  
  
 クラス型のデータまたはクラスを返す関数をエクスポートする場合、必ずそのクラスもエクスポートしてください。  
  
##  <a name="_pluslang_dllexport_classesdllexportclasses"></a> dllimport クラス  
 クラスを宣言するときに**dllimport**、すべてのメンバー関数と静的データ メンバーがインポートされます。 動作とは異なり**dllimport**と**dllexport** 、クラス型に対する静的データ メンバーを同じプログラム内で定義を指定できない、 **dllimport**クラス定義されています。  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2binheritanceandexportableclasses"></a> 継承とエクスポート可能クラス  
 エクスポート可能なクラスのすべての基底クラスはエクスポート可能である必要があります。 そうでない場合、コンパイラ警告が生成されます。 また、クラスでもあるアクセス可能なメンバーはすべてエクスポート可能である必要があります。 この規則によって許可、 **dllexport**から継承するクラス、 **dllimport**クラス、および**dllimport**から継承するクラス、 **dllexport**クラスの (ただし、後者は推奨されません)。 一般的に、DLL のクライアントからアクセス可能な (C++ のアクセス規則に従って) すべてのものは、エクスポート可能なインターフェイスの一部である必要があります。 たとえば、インライン関数で参照されるプライベート データ メンバーなどです。  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bselectivememberimportexport"></a> 選択的なメンバーのインポート/エクスポート  
 メンバー関数と静的データ クラス内で暗黙的に外部リンケージがある、ためには、それらを宣言、 **dllimport**または**dllexport**属性は、クラス全体をエクスポートしない限り、します。 クラス全体をインポートまたはエクスポート、メンバー関数とデータとしての明示的な宣言**dllimport**または**dllexport**は禁止されています。 静的データ メンバーとしてクラス定義内で宣言する**dllexport**定義を行う必要がありますどこかに、同じプログラム内で (非クラス外部リンケージ) と同様です。  
  
 同様に、できるメンバーを宣言する関数を**dllimport**または**dllexport**属性。 この場合は、指定する必要があります、 **dllexport**同じプログラム内のどこか定義します。  
  
 選択的なメンバーのインポート/エクスポートには、次のいくつかの重要な点に注意してください。  
  
-   選択的なメンバーのインポート/エクスポートは、より制限が厳しい、エクスポートされたクラス インターフェイスのバージョン (つまり、言語で許容されるよりも少ないパブリック機能およびプライベート機能を公開する DLL を設計できるバージョン) を提供する場合に最適です。 また、エクスポート可能なインターフェイスを最適化するためにも便利です。クライアントがプライベート データにアクセスできない場合は、もちろん、クラス全体をエクスポートする必要はありません。  
  
-   クラス内の 1 つの仮想関数をエクスポートする場合、それらの関数のすべてをエクスポートするか、少なくともクライアントが直接使用できるバージョンを提供する必要があります。  
  
-   仮想関数で使用する選択的なメンバーのインポート/エクスポートを行うクラスがある場合、それらの関数はエクスポート可能なインターフェイスまたは定義済みインライン内 (クライアントから参照可能) にある必要があります。  
  
-   としてメンバーを定義する場合**dllexport**クラス定義には含まれませんは、コンパイラ エラーが生成されます。 クラスのヘッダーでメンバーを定義する必要があります。  
  
-   クラス メンバーの定義**dllimport**または**dllexport**は許可されている場合、クラス定義で指定されたインターフェイスをオーバーライドすることはできません。  
  
-   宣言をクラス定義の本体以外では、メンバー関数を定義する場合と、関数が定義されている場合に警告が生成**dllexport**または**dllimport** (場合この定義とは異なります、クラス宣言で指定されている)。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [dllexport、dllimport](../cpp/dllexport-dllimport.md)