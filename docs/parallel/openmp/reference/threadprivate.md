---
title: threadprivate |Microsoft ドキュメント
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
ms.openlocfilehash: e7e7edaa36f929750087e3c81f42204ff20e9f62
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="threadprivate"></a>threadprivate
変数が、スレッドに対してプライベートであることを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma omp threadprivate(var)  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `var`  
 スレッドにプライベートに変数のコンマ区切り一覧。 `var` グローバルまたは名前空間スコープの変数または静的ローカル変数のいずれかにする必要があります。  
  
## <a name="remarks"></a>コメント  
 `threadprivate`ディレクティブに OpenMP 句がサポートされていません。  
  
 詳細については、次を参照してください。 [2.7.1 threadprivate ディレクティブ](../../../parallel/openmp/2-7-1-threadprivate-directive.md)です。  
  
 `threadprivate`ディレクティブがに基づいて、[スレッド](../../../cpp/thread.md)`__declspec`属性; 制限 **_declspec**に適用`threadprivate`です。  
  
 使用することはできません`threadprivate`経由で読み込まれる DLL を任意で[LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175)です。  これで読み込まれる Dll に含まれます[/DELAYLOAD (遅延読み込みのインポート)](../../../build/reference/delayload-delay-load-import.md)を使用しても**LoadLibrary**です。  
  
 使用することができます`threadprivate`プロセスの起動時に静的に読み込まれる DLL にします。  
  
 `threadprivate`に基づく **_declspec**、`threadprivate`変数は、並行領域によって生成されるスレッド チームの一部であるスレッドだけでなく、プロセスで開始された任意のスレッド内に存在します。  これは、する可能性がありますので、たとえばのコンス トラクターに、認識する実装の詳細、`threadprivate`予想以上にユーザー定義型が呼び出されます。  
  
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
  
 ユーザーを掌握ありません並列領域を構成するスレッドが終了されますか。  プロセスが終了するし、スレッドはプロセスの終了に関する通知されませんのデストラクターを呼び出すことはできません、それらのスレッドが存在しない場合`threaded_var`終了を除く任意のスレッドで (ここで、プライマリ スレッド)。  コードの適切な破棄をカウントしませんように`threadprivate`変数。  
  
## <a name="example"></a>例  
 使用するサンプルの`threadprivate`を参照してください[プライベート](../../../parallel/openmp/reference/private-openmp.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ](../../../parallel/openmp/reference/openmp-directives.md)