---
title: code_seg |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- code_seg_CPP
- vc-pragma.code_seg
dev_langs:
- C++
helpviewer_keywords:
- pragmas, code_seg
- code_seg pragma
ms.assetid: bf4faac1-a511-46a6-8d9e-456851d97d56
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 052e9a55d443fa263ecf8443c9e3933baeb1f3b8
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42540884"
---
# <a name="codeseg"></a>code_seg
関数が格納される .obj ファイル内のテキスト セグメントを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma code_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Remarks  
 
**Code_seg**プラグマ ディレクティブは、インスタンス化されたテンプレートは、生成されたオブジェクト コードも、コンパイラによって暗黙的に生成されたコードの配置を制御しません-たとえば、特殊なメンバー関数。 使用することをお勧め、 [__declspec(code_seg(...)](../cpp/code-seg-declspec.md)属性の代わりに使用するすべてのオブジェクト コードの配置を制御します。 コンパイラによって生成されたコードの格納場所も制御できるためです。  
  
A*セグメント*.obj ファイルは名前付きのユニットとしてメモリに読み込まれるデータのブロック。 A*テキスト セグメント*は実行可能コードを含むセグメントです。 この記事で、条項*セグメント*と*セクション*は同義です。  
  
**Code_seg**プラグマ ディレクティブを指定すると、翻訳単位からの後続のオブジェクトのすべてのコードをという名前のテキスト セグメントに配置*セグメント名*します。 既定では、.obj ファイル内の関数に使用されるテキスト セグメントには .text という名前が付けられます。  
  
A **code_seg**プラグマ ディレクティブ パラメーターを指定せず、後続のオブジェクト コードのテキスト セグメント名を .text にリセットします。  
  
*プッシュ*(省略可能)  
レコードを内部コンパイラ スタックに格納します。 A*プッシュ*できますが、*識別子*と*セグメント名*します。  
  
*pop* (省略可能)  
内部コンパイラ スタックの最上部からレコードを削除します。  
  
*識別子*(省略可能)  
使用すると*プッシュ*、内部コンパイラ スタックのレコードに名前を割り当てます。 使用すると*pop*、レコードまで内部スタックからポップ*識別子*が削除された場合*識別子*は内部のスタックに何もポップされます。  
  
*識別子*により、複数のレコードを 1 つだけでポップできます*pop*コマンド。  
  
"*セグメント名*"(省略可能)  
引数の名前。 使用すると*pop*、スタックがポップされ、*セグメント名*アクティブなテキスト セグメント名になります。  
  
"*セグメント クラス*"(省略可能)  
無視されますが、C++ 2.0 より前のバージョンとの互換性を保つために残されています。  
  
使用することができます、 [DUMPBIN します。EXE](../build/reference/dumpbin-command-line.md) .obj ファイルを表示するアプリケーション。 各サポートされているターゲット アーキテクチャの DUMPBIN のバージョンは Visual Studio に含まれています。  
  
## <a name="example"></a>例  

この例は、使用する方法を示します、 **code_seg**プラグマ ディレクティブをオブジェクト コードの格納場所を制御します。  
  
```cpp  
// pragma_directive_code_seg.cpp  
void func1() {                  // stored in .text  
}  
  
#pragma code_seg(".my_data1")  
void func2() {                  // stored in my_data1  
}  
  
#pragma code_seg(push, r1, ".my_data2")  
void func3() {                  // stored in my_data2  
}  
  
#pragma code_seg(pop, r1)      // stored in my_data1  
void func4() {  
}  
  
int main() {  
}  
```  
  
セクションを作成する使わないで名の一覧は、次を参照してください。 [/section](../build/reference/section-specify-section-attributes.md)します。  
  
初期化されたデータのセクションを指定することもできます ([data_seg](../preprocessor/data-seg.md))、初期化されていないデータ ([bss_seg](../preprocessor/bss-seg.md))、および const 変数 ([const_seg](../preprocessor/const-seg.md))。  
  
## <a name="see-also"></a>関連項目  
 
[code_seg (_ _declspec)](../cpp/code-seg-declspec.md)   
[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)