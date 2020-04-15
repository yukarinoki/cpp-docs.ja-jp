---
title: C++ クラスでの dllimport と dllexport の使用
ms.date: 11/04/2016
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
ms.openlocfilehash: c0a2c96a37f58c956976980beafd5ecbed4d1318
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365119"
---
# <a name="using-dllimport-and-dllexport-in-c-classes"></a>C++ クラスでの dllimport と dllexport の使用

**マイクロソフト固有**

c++ クラスは **、dllimport**属性または**dllexport**属性を使用して宣言できます。 これらの形式は、クラス全体がインポートまたはエクスポートされることを暗黙的に指定します。 この方法でエクスポートされたクラスは、エクスポート可能なクラスと呼ばれます。

次の例では、エクスポート可能なクラスを定義しています。 そのメンバー関数と静的データはすべてエクスポートされます。

```cpp
#define DllExport   __declspec( dllexport )

class DllExport C {
   int i;
   virtual int func( void ) { return 1; }
};
```

エクスポート可能なクラスのメンバーに対して**dllimport**属性と**dllexport**属性を明示的に使用することは禁止されています。

## <a name="dllexport-classes"></a><a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bdllexportclasses"></a>dll エクスポート クラス

クラス**dllexport**を宣言すると、そのメンバー関数と静的データ メンバーがすべてエクスポートされます。 このようなすべてのメンバーは同じプログラム内で定義する必要があります。 定義しない場合は、リンカー エラーが生成されます。 この規則の例外は純粋仮想関数です。純粋仮想関数にはこのような明示的な定義は不要です。 ただし、抽象クラスのデストラクターは基底クラスのデストラクターによって常に呼び出されるため、純粋仮想デストラクターには常に明示的な定義が必要です。 これらの規則はエクスポート不可クラスに対しても同じであることに注意してください。

クラス型のデータまたはクラスを返す関数をエクスポートする場合、必ずそのクラスもエクスポートしてください。

## <a name="dllimport-classes"></a><a name="_pluslang_dllexport_classesdllexportclasses"></a>dll インポート クラス

クラス**dllimport**を宣言すると、そのメンバー関数と静的データ メンバーがすべてインポートされます。 非クラス型で**の dllimport**および**dllexport**の動作とは異なり、静的データ メンバーは **、dllimport**クラスが定義されているのと同じプログラムで定義を指定できません。

## <a name="inheritance-and-exportable-classes"></a><a name="_pluslang_using_dllimport_and_dllexport_in_c2b2binheritanceandexportableclasses"></a>継承とエクスポート可能なクラス

エクスポート可能なクラスのすべての基底クラスはエクスポート可能である必要があります。 そうでない場合、コンパイラ警告が生成されます。 また、クラスでもあるアクセス可能なメンバーはすべてエクスポート可能である必要があります。 この規則では **、dllexport**クラスが**dllimport**クラスから継承され **、dllimport**クラスが**dllexport**クラスから継承することを許可します (ただし、後者は推奨されません)。 一般的に、DLL のクライアントからアクセス可能な (C++ のアクセス規則に従って) すべてのものは、エクスポート可能なインターフェイスの一部である必要があります。 たとえば、インライン関数で参照されるプライベート データ メンバーなどです。

## <a name="selective-member-importexport"></a><a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bselectivememberimportexport"></a>選択的メンバーのインポート/エクスポート

メンバー関数とクラス内の静的データは暗黙的に外部リンケージを持つため、クラス全体がエクスポートされない限り **、dllimport**属性または**dllexport**属性を使用して宣言できます。 クラス全体がインポートまたはエクスポートされる場合、メンバー関数とデータを**dllimport**または**dllexport**として明示的に宣言することは禁止されています。 クラス定義内で静的データ メンバーを**dllexport**として宣言する場合は、定義が同じプログラム内のどこかで (クラス以外の外部リンケージの場合と同様) 必要があります。

同様に **、dllimport**属性または**dllexport**属性を使用してメンバー関数を宣言できます。 この場合、同じプログラム内のどこかに**dllexport**定義を指定する必要があります。

選択的なメンバーのインポート/エクスポートには、次のいくつかの重要な点に注意してください。

- 選択的なメンバーのインポート/エクスポートは、より制限が厳しい、エクスポートされたクラス インターフェイスのバージョン (つまり、言語で許容されるよりも少ないパブリック機能およびプライベート機能を公開する DLL を設計できるバージョン) を提供する場合に最適です。 また、エクスポート可能なインターフェイスを最適化するためにも便利です。クライアントがプライベート データにアクセスできない場合は、もちろん、クラス全体をエクスポートする必要はありません。

- クラス内の 1 つの仮想関数をエクスポートする場合、それらの関数のすべてをエクスポートするか、少なくともクライアントが直接使用できるバージョンを提供する必要があります。

- 仮想関数で使用する選択的なメンバーのインポート/エクスポートを行うクラスがある場合、それらの関数はエクスポート可能なインターフェイスまたは定義済みインライン内 (クライアントから参照可能) にある必要があります。

- メンバーを**dllexport**として定義し、クラス定義に含まれていない場合は、コンパイラ エラーが生成されます。 クラスのヘッダーでメンバーを定義する必要があります。

- **dllimport**または**dllexport**としてクラス メンバーの定義は許可されていますが、クラス定義で指定されたインターフェイスをオーバーライドすることはできません。

- メンバー関数を宣言したクラス定義の本体以外の場所で定義すると、その関数が**dllexport**または**dllimport**として定義されている場合 (この定義がクラス宣言で指定された関数と異なる場合)、警告が生成されます。

**エンド マイクロソフト 固有**

## <a name="see-also"></a>関連項目

[dllexport、dllimport](../cpp/dllexport-dllimport.md)
