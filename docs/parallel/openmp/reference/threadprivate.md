---
title: threadprivate |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- threadprivate
dev_langs:
- C++
helpviewer_keywords:
- threadprivate OpenMP directive
ms.assetid: 3515aaed-6f9d-4d59-85eb-342378bea2d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9454b33348fa4e4bc2efaa609001201ea215a8c9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081989"
---
# <a name="threadprivate"></a>threadprivate
変数は、スレッドに対してプライベートであることを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma omp threadprivate(var)  
```  
  
### <a name="parameters"></a>パラメーター
  
*var*<br/>
スレッドに非公開にする変数のコンマ区切りの一覧。 `var` グローバルまたは名前空間スコープの変数または静的ローカル変数のいずれかである必要があります。  
  
## <a name="remarks"></a>Remarks  
 `threadprivate`ディレクティブに OpenMP 句がサポートされていません。  
  
 詳細については、次を参照してください。 [2.7.1 threadprivate ディレクティブ](../../../parallel/openmp/2-7-1-threadprivate-directive.md)します。  
  
 `threadprivate`ディレクティブがに基づいて、[スレッド](../../../cpp/thread.md)`__declspec`属性に制限します。 **_declspec**適用`threadprivate`します。  
  
 使用することはできません`threadprivate`経由で読み込まれる DLL で[LoadLibrary](https://msdn.microsoft.com/library/windows/desktop/ms684175)します。  これで読み込まれる Dll が含まれます[/DELAYLOAD (遅延読み込みのインポート)](../../../build/reference/delayload-delay-load-import.md)も使用する**LoadLibrary**します。  
  
 使用することができます`threadprivate`プロセスの起動時に静的に読み込まれる DLL にします。  
  
 `threadprivate`に基づいて **_declspec**、`threadprivate`変数は、任意のスレッドが並列領域により生成されたスレッド チームの一部であるスレッドだけでなく、プロセスの開始に存在します。  これはお気付き、たとえば、コンス トラクターのため、注意するが必要な実装の詳細、`threadprivate`予想以上にユーザー定義型が呼び出されます。  
  
 A`threadprivate`消滅可能型の変数と呼ばれる、デストラクターは保証されません。  例えば:  
  
```  
struct MyType   
{  
    ~MyType();  
};  
  
MyType threaded_var;  
#pragma omp threadprivate(threaded_var)  
int main()   
{  
    #pragma omp parallel  
    {}  
}  
```  
  
 ユーザーは、並列領域を構成するスレッドが終了すると、コントロールを持つありません。  プロセスが終了するし、スレッドはプロセスの終了に関する通知されませんのデストラクターは呼び出されません、それらのスレッドが存在しない場合`threaded_var`に存在する 1 つを除く任意のスレッドで (ここでは、プライマリ スレッド)。  コードの適切な破棄をカウントしませんように`threadprivate`変数。  
  
## <a name="example"></a>例  
 使用するサンプルの`threadprivate`を参照してください[プライベート](../../../parallel/openmp/reference/private-openmp.md)します。  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ](../../../parallel/openmp/reference/openmp-directives.md)