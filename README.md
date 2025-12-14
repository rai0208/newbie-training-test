<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>社内教育テスト（自由記述提出用）</title>
  <style>
    :root {
      --primary-color: #2563eb;
      --primary-hover: #1d4ed8;
      --success-color: #10b981;
      --bg-color: #f3f4f6;
      --card-bg: #ffffff;
      --text-main: #1f2937;
      --text-sub: #6b7280;
      --border-color: #e5e7eb;
    }

    body {
      font-family: "Helvetica Neue", Arial, "Hiragino Kaku Gothic ProN", "Hiragino Sans", Meiryo, sans-serif;
      margin: 0;
      padding: 20px;
      background: var(--bg-color);
      color: var(--text-main);
      line-height: 1.6;
    }

    .container {
      max-width: 700px;
      margin: 0 auto;
    }

    .card {
      background: var(--card-bg);
      border-radius: 12px;
      padding: 24px;
      box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
      margin-bottom: 20px;
      transition: all 0.3s ease;
    }

    h1 {
      text-align: center;
      font-size: 1.5rem;
      margin-bottom: 24px;
      color: var(--text-main);
    }

    h2 {
      font-size: 1.25rem;
      margin-top: 0;
      border-bottom: 2px solid var(--primary-color);
      padding-bottom: 8px;
      display: inline-block;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      width: 100%;
      padding: 12px 20px;
      border-radius: 8px;
      border: none;
      font-size: 1rem;
      font-weight: 600;
      cursor: pointer;
      transition: background-color 0.2s, transform 0.1s;
      margin-bottom: 12px;
      text-decoration: none;
      text-align: center;
      box-sizing: border-box;
    }

    .btn:active {
      transform: scale(0.98);
    }

    .btn-primary {
      background: var(--primary-color);
      color: white;
    }

    .btn-primary:hover {
      background: var(--primary-hover);
    }
    
    .btn-success {
      background: var(--success-color);
      color: white;
    }
    
    .btn-success:hover {
      background: #059669;
    }

    .btn-secondary {
      background: white;
      color: var(--primary-color);
      border: 2px solid var(--primary-color);
    }

    .btn-secondary:hover {
      background: #eff6ff;
    }

    textarea {
      width: 100%;
      min-height: 100px;
      padding: 12px;
      border-radius: 8px;
      border: 1px solid var(--border-color);
      font-size: 1rem;
      font-family: inherit;
      resize: vertical;
      margin-bottom: 16px;
      box-sizing: border-box;
    }

    textarea:focus {
      outline: none;
      border-color: var(--primary-color);
      box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.1);
    }
    
    input[type="text"] {
      width: 100%;
      padding: 12px;
      border-radius: 8px;
      border: 1px solid var(--border-color);
      font-size: 1rem;
      font-family: inherit;
      margin-bottom: 20px;
      box-sizing: border-box;
    }

    input[type="text"]:focus {
      outline: none;
      border-color: var(--primary-color);
      box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.1);
    }

    .hidden { display: none !important; }
    .fade-in { animation: fadeIn 0.3s ease-in; }
    .text-center { text-align: center; }
    .mt-4 { margin-top: 16px; }
    .mb-2 { margin-bottom: 8px; }
    
    .badge {
      display: inline-block;
      padding: 4px 8px;
      border-radius: 4px;
      font-size: 0.85rem;
      font-weight: bold;
      background: #e0e7ff;
      color: #3730a3;
      margin-bottom: 8px;
    }

    .progress-container {
      background: #e5e7eb;
      border-radius: 999px;
      height: 8px;
      margin-bottom: 20px;
      overflow: hidden;
    }
    .progress-bar {
      background: var(--primary-color);
      height: 100%;
      width: 0%;
      transition: width 0.3s ease;
    }

    .label {
      font-size: 0.75rem;
      color: var(--text-sub);
      font-weight: bold;
      text-transform: uppercase;
      margin-bottom: 4px;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>

<div class="container">
  <h1>社内教育テスト <span style="font-size:0.6em; color:#666;">（自由記述提出用）</span></h1>

  <!-- 1. Start Screen -->
  <div id="start-screen" class="card fade-in">
    <h2 class="text-center">コース選択</h2>
    
    <div style="margin-top: 20px;">
      <div class="label">受験者名（必須）</div>
      <input type="text" id="user-name-input" placeholder="氏名を入力してください" required>
    </div>

    <p class="text-center mb-2" style="margin-top: 20px;">
      挑戦するレベルを選択してください。（各レベル10問をランダムに出題します）
    </p>
    <div style="margin-top: 12px;">
      <button class="btn btn-primary" onclick="app.startQuiz(1)">
        <div><strong>Lv1：基礎知識</strong><br>
          <span style="font-size:0.85em; font-weight:normal;">主要部材の名称や役割の基礎（ランダム10問）</span>
        </div>
      </button>
      <button class="btn btn-primary" onclick="app.startQuiz(2)">
        <div><strong>Lv2：システム理解</strong><br>
          <span style="font-size:0.85em; font-weight:normal;">換気方式の特徴や設置・運用時の注意点（ランダム10問）</span>
        </div>
      </button>
      <button class="btn btn-primary" onclick="app.startQuiz(3)">
        <div><strong>Lv3：実践応用</strong><br>
          <span style="font-size:0.85em; font-weight:normal;">風量・静圧の関係、トラブルシューティング、計算基礎（ランダム10問）</span>
        </div>
      </button>
    </div>
  </div>

  <!-- 2. Quiz Screen -->
  <div id="quiz-screen" class="card hidden">
    <div class="progress-container">
      <div id="progress-bar" class="progress-bar"></div>
    </div>
    <div class="text-center mb-2">
      <span id="question-count" class="badge">Q 1/10</span>
    </div>
    
    <h3 id="question-text" style="font-size:1.2rem; margin-bottom:16px;">ここに問題が表示されます</h3>
    
    <div class="label">あなたの回答</div>
    <textarea id="answer-input" placeholder="ここに回答を入力してください"></textarea>
    
    <div style="display:flex; gap:12px; margin-top:4px;">
      <button id="prev-btn" class="btn btn-secondary" style="flex:1;">前の問題に戻る</button>
      <button id="submit-btn" class="btn btn-primary" style="flex:1;">次へ進む</button>
    </div>
  </div>

  <!-- 3. Result Screen (Submission) -->
  <div id="result-screen" class="card hidden">
    <h2 class="text-center">回答完了</h2>
    
    <p class="text-center" style="margin-top: 20px; font-weight: bold;">
      お疲れ様でした。回答内容を上長に提出してください。
    </p>

    <div class="label" style="margin-top: 20px;">あなたの回答内容（自動生成）</div>
    <textarea id="send-text" readonly style="min-height: 250px; font-size: 0.85rem; color:#555; background:#f9fafb;"></textarea>
    
    <button id="action-btn" class="btn mt-4"></button>
    <div id="copy-message" class="text-center hidden" style="color:var(--success-color); font-weight:bold; margin-top:-8px; margin-bottom:12px;"></div>

    <button class="btn btn-secondary mt-4" onclick="location.reload()">トップに戻る</button>
  </div>

</div>

<script>
/**
 * Test Application Logic
 * 自己採点なし・自由記述提出ツール
 */
window.app = {
  // Constants
  NUM_QUESTIONS: 10,
  MAILTO_LIMIT: 10000, // mailtoの文字数制限（エンコード後）

  // State
  questions: [],
  currentLevel: 0,
  currentIndex: 0,
  userAnswers: [], // indexごとに { question, userText }
  userName: '', 

  // 問題データ
  database: [
    // --- Lv1：基礎知識 (20問) ---
    { id: 1, level: 1, text: "ダクト内を流れる風量を調整するためのダンパーを何と言いますか？", model: "VD（Volume Damper）。風量調整ダンパー。ダクト内の風量を調整し、各系統のバランスを整える部材。" },
    { id: 2, level: 1, text: "FDの正式名称と役割を説明してください。", model: "FD（Fire Damper）。防火ダンパー。火災時にヒューズが溶けて閉鎖し、延焼を防ぐ。" },
    { id: 3, level: 1, text: "グラスウールとロックウールの使い分けを説明してください。", model: "グラスウールは主に保温・保冷（一般空調）。ロックウールは耐火・耐熱性が高く、厨房排気や高温ダクトに使用する。" },
    { id: 4, level: 1, text: "セラカバーの主な用途は何ですか？", model: "ロックウールの成形品で、主に厨房排気ダクトの断熱・防火措置に使用する。施工が容易。" },
    { id: 5, level: 1, text: "フレキシブルダクトの使用上の注意点は？（長さなど）", model: "抵抗が大きいため、必要最小限（一般的に2m以内）にする。曲がりを急にしない。" },
    { id: 6, level: 1, text: "キャンバスダクト（たわみ継手）の役割は？", model: "送風機などの振動をダクトに伝えないための防振継手。" },
    { id: 7, level: 1, text: "厨房排気で「ニューホープ」等の耐油性フレキを使う理由は？", model: "一般のアルミフレキは油や熱で腐食・穴あきが発生しやすいため。耐久性を確保するため。" },
    { id: 8, level: 1, text: "外壁ガラリに防虫網を付けるメリットとデメリットは？", model: "メリット：虫の侵入防止。デメリット：目詰まりしやすく、メンテナンスを怠ると給気不足になる。" },
    { id: 9, level: 1, text: "グリスフィルターの役割を説明してください。", model: "油脂分を除去し、ダクト内への油の侵入を防ぐ。火災延焼防止機能（F値）を持つものもある。" },
    { id: 10, level: 1, text: "火災時に防火区画の延焼を防ぐために、一定温度に達すると自動で閉鎖するダンパーを何と言いますか？", model: "防火ダンパー。火災時にヒューズが溶けて閉鎖し、延焼を防ぐ。" },
    { id: 11, level: 1, text: "給気ダクトに断熱材を巻く主な目的を2つ説明してください。", model: "①結露防止（特に冷房時の給気）。②熱損失防止（暖房時）。③消音効果（限定的）。" },
    { id: 12, level: 1, text: "角ダクトと丸ダクトの一般的な使い分けを説明してください。", model: "角ダクトは天井裏のスペース制限がある場合や分岐が多い場所。丸ダクトは抵抗が少なく、漏れにくいが、省スペース化が難しい。" },
    { id: 13, level: 1, text: "SAとRAの正式名称と意味を説明してください。", model: "SA: Supply Air（給気）。RA: Return Air（還気）。" },
    { id: 14, level: 1, text: "フレキダクトの接続部に使われるアルミテープの役割は？", model: "ダクト内の気密性を保ち、空気の漏れを防ぐこと。耐火・耐熱性も確保するため。" },
    { id: 15, level: 1, text: "防火区画を貫通するダクトにFDを設置する理由を説明してください。", model: "火災の熱による煙や炎が、ダクトを通じて他の防火区画へ広がるのを防ぐため。" },
    { id: 16, level: 1, text: "キャンバスダクト（防振ジョイント）を設置する機器を2つ挙げてください。", model: "シロッコファン、ミニシロッコファン、ストレートシロッコファンなど。" },
    { id: 17, level: 1, text: "ダクトの継手部分で、空気の漏れ（リーク）を防ぐための一般的な対策は？", model: "パッキン、シーリング材（コーキング）、気密テープの使用。" },
    { id: 18, level: 1, text: "屋外に設置するダクトやフードの防錆対策について説明してください。", model: "亜鉛メッキ鋼板（ガルバリウム鋼板など）を使用する。必要に応じて塗装仕上げとする。" },
    { id: 19, level: 1, text: "排気ダクトの途中に設ける「点検口」の役割は？", model: "ダクト内の清掃、FD（防火ダンパー）のヒューズ交換、VDの調整など、メンテナンスのため。" },
    { id: 20, level: 1, text: "一般空調のダクト内張り材として使用される材料を一つ挙げてください。", model: "グラスウール、またはポリエチレンフォームなどの断熱材。" },

    // --- Lv2：システム理解 (20問) ---
    { id: 21, level: 2, text: "第1種換気の特徴とメリットを説明してください。", model: "給気・排気ともに機械で行う方式。室圧コントロールが容易で、確実な換気ができる。" },
    { id: 22, level: 2, text: "第3種換気が厨房に適している理由（または一般的である理由）は？", model: "排気のみ機械で行うため室内が負圧になり、厨房の臭気や熱気が客席へ流出しにくいため。" },
    { id: 23, level: 2, text: "飲食店で第2種換気（給気のみ機械）がNGとされる理由は？", model: "室内が正圧になり、臭気が外部や他区画へ漏れ出すため。" },
    { id: 24, level: 2, text: "ショートサーキットとはどのような現象ですか？", model: "給気口と排気口が近すぎて、給気した空気がそのまま排気されてしまい、換気が行われない現象。" },
    { id: 25, level: 2, text: "「負圧が強すぎてドアが開かない」場合の対策は？", model: "給気量を増やす、または排気量を絞って室内の負圧を弱める。" },
    { id: 26, level: 2, text: "無煙ロースター（下方排気）の施工上のデメリット・注意点は？", model: "床下にダクトを通すため、配管勾配（油だまり）や清掃口の設置、防水対策が必要。コストも高い。" },
    { id: 27, level: 2, text: "ダクト内風速が速すぎることの弊害を2つ挙げてください。", model: "①騒音（風切り音）の発生。②圧力損失の増大（ファンへの負荷増）。" },
    { id: 28, level: 2, text: "給気口の配置で、客席において注意すべきことは？", model: "ドラフト（不快な気流）が客に直接当たらない位置・風速にすること。" },
    { id: 29, level: 2, text: "厨房フードの「面風速」の目安は？", model: "一般的に0.3m/s〜0.5m/s程度。" },
    { id: 30, level: 2, text: "インバーター制御をファンに導入するメリットは？", model: "周波数を変えて風量を調整できるため、試運転調整が容易で、省エネ効果も見込める。" },
    { id: 31, level: 2, text: "全熱交換器（ロスナイなど）の設置目的とデメリットを説明してください。", model: "目的：排気熱を回収し、外気の給気温度を近づけることで空調負荷を軽減。デメリット：排気側と給気側の空気が混ざり、臭気が戻る場合がある。" },
    { id: 32, level: 2, text: "換気設備における「結露」の主な発生原因と対策は？", model: "原因：ダクト表面温度と周囲空気温度の差。対策：断熱材の適切な施工、または温度差を少なくする。" },
    { id: 33, level: 2, text: "VAV（可変風量）システムとCAV（定風量）システムの使い分けは？", model: "VAV：負荷変動に応じて風量を変え、省エネに優れる。CAV：一定風量で室圧・温湿度管理を安定させる。" },
    { id: 34, level: 2, text: "防火ダンパー（FD）と排煙ダンパー（SD）の動作原理の違いを説明してください。", model: "FD：ヒューズが溶けて自動閉鎖（防火）。SD：火災感知器と連動して遠隔操作で開閉（排煙）。" },
    { id: 35, level: 2, text: "天井裏をダクトルートとして利用する際の注意点を2つ以上挙げてください。", model: "①点検口の確保。②他の設備（電気配線、配管）との干渉回避。③ダクトの気密性確保。" },
    { id: 36, level: 2, text: "換気風量を決定する際に考慮すべき3つの主要な要素は？", model: "①在室人数。②室用途（汚染物質の発生量）。③法令で定められた換気回数。" },
    { id: 37, level: 2, text: "厨房排気ファンでベルト駆動式が多い理由を説明してください。", model: "プーリー交換で容易に風量調整ができ、モーターを熱や油汚れから離して配置できるため。" },
    { id: 38, level: 2, text: "吸込み口と吐出し口が同一の外部フードにある場合の、ファン能力への影響は？", model: "ショートサーキットを起こし、新鮮外気が取り込めず、汚れた空気を再吸込みしやすい。" },
    { id: 39, level: 2, text: "風量測定値が設計値と大きく異なる場合に確認すべき点を2つ挙げてください。", model: "①VD（ダンパー）が全開か。②ファン回転数（インバータ設定、プーリー径）が設計通りか。③ダクトの漏れ・閉塞がないか。" },
    { id: 40, level: 2, text: "排煙設備の「自然排煙」と「機械排煙」の使い分けを説明してください。", model: "自然排煙：窓などの開口部を利用。機械排煙：排煙機（ファン）を利用。条件により自然排煙のみで可のケースもある。" },

    // --- Lv3：実践応用 (21問目まで追加済) ---
    { id: 41, level: 3, text: "風量 Q (m³/h) を求める基本式は？（風速V、面積Aを使って）", model: "Q = A × V × 3600 （A:断面積[m²], V:風速[m/s]）" },
    { id: 42, level: 3, text: "ダクトの「アスペクト比」とは何か。推奨される制限は？", model: "ダクトの長辺と短辺の比率。一般に4:1以下が望ましい。" },
    { id: 43, level: 3, text: "静圧（Ps）、動圧（Pv）、全圧（Pt）の関係式は？", model: "Pt = Ps + Pv （全圧 = 静圧 + 動圧）" },
    { id: 44, level: 3, text: "ダクト径を半分にすると、抵抗（圧損）は理論上どうなるか？", model: "同じ風量を流そうとすると流速が4倍になり、圧損は大幅に増加する。" },
    { id: 45, level: 3, text: "送風機の「サージング」とはどのような現象か？", model: "風量・圧力が周期的に変動し、激しい振動や騒音を伴う不安定運転現象。" },
    { id: 46, level: 3, text: "システム天井などでリターン（還気）を取る際の「天井内負圧」のリスクは？", model: "天井ボードの吸い上げ、ドアの開閉障害、排水トラップの破封、隙間風の音など。" },
    { id: 47, level: 3, text: "長方形ダクトを正方形や円形に換算した直径を何と呼ぶか？", model: "相当直径（等価直径）。" },
    { id: 48, level: 3, text: "シロッコファンとターボファンの特性の違いは（静圧の観点で）？", model: "ターボファンは高静圧・高効率。シロッコファンは静圧は低いが風量が取れ、小型。" },
    { id: 49, level: 3, text: "厨房排気ファンの選定で、静圧計算時に特に考慮すべき抵抗要素は？", model: "グリスフィルター、防火ダンパー、防虫網、外部フード、および油汚れによる経年劣化分。" },
    { id: 50, level: 3, text: "CO2濃度センサーによる換気制御の目的は？", model: "在室人数に応じて必要換気量を調整し、外気導入負荷（空調エネルギー）を削減するため。" },
    { id: 51, level: 3, text: "インバーターでファンの回転数を1/2に下げた場合、風量・静圧・消費電力は理論上どうなるか？", model: "風量は1/2、静圧は1/4、消費電力は1/8になる（ファン相似則）。" },
    { id: 52, level: 3, text: "局所排気の設計において、フードの捕集効率を上げるための基本的な考え方は？", model: "①フードを発生源にできるだけ近づける。②発生源を囲い込む。③周りの気流を乱さない。" },
    { id: 53, level: 3, text: "ダクト曲がり部（エルボ）の抵抗（圧損）を減らすための工夫を2つ挙げてください。", model: "①曲がり半径を大きくする。②案内羽根（ガイドベーン）を設ける。" },
    { id: 54, level: 3, text: "TAB（Testing, Adjusting and Balancing）作業の最終的な目的を説明してください。", model: "設計図通りの風量・静圧・温湿度が各吹出口・吸込口で確実に出ている状態に調整すること。" },
    { id: 55, level: 3, text: "静圧測定に使う「ピトー管」の測定原理を説明してください。", model: "全圧と静圧の差から動圧を求め、その値から風速を算出する。" },
    { id: 56, level: 3, text: "高層ビルの換気計画で考慮すべき「スタック効果（煙突効果）」とは何か？", model: "建物の内外の温度差・密度差により、上下方向の自然気流が発生する現象。" },
    { id: 57, level: 3, text: "空調機のAHUで加湿器を設置する主な目的と、加湿方式を一つ挙げてください。", model: "目的：冬季の乾燥対策や湿度管理。方式：蒸気式、気化式、噴霧式などのいずれか。" },
    { id: 58, level: 3, text: "ファン騒音対策として、ダクト経路に追加できる部材を2つ挙げてください。", model: "①サイレンサー（消音器）。②内張り消音ダクト。③内張り付きチャンバーボックス。" },
    { id: 59, level: 3, text: "ダクト内の空気抵抗は、ダクトの長さと内壁の粗さ（摩擦係数）にどう影響を受けるか？", model: "長さが長いほど、内面が粗いほど抵抗は大きくなる。" },
    { id: 60, level: 3, text: "圧力損失（圧損）を低減するための設計上の工夫を2つ挙げてください。", model: "①ダクトの風速を下げる（径を大きくする）。②エルボや分岐をなだらかにする。③内面を滑らかにする。" },
    { id: 61, level: 3, text: "チャンバーボックスの役割を2つ挙げてください。", model: "①分岐や合流をスムーズにする。②消音効果（内貼りがある場合）。" }
  ],

  // Methods
  startQuiz: function(level) {
    const userNameInput = document.getElementById('user-name-input');
    const name = userNameInput.value.trim();

    if (!name) {
      this.showMessage('受験者名を入力してください。');
      userNameInput.focus();
      return;
    }

    this.userName = name;
    this.currentLevel = level;

    // レベル別に絞ってシャッフル
    const levelQuestions = this.database.filter(q => q.level === level);

    if (levelQuestions.length < this.NUM_QUESTIONS) {
      this.showMessage(`エラー: レベル${level}の問題が${this.NUM_QUESTIONS}問未満です。（${levelQuestions.length}問のみ）`);
      this.questions = this.shuffleArray([...levelQuestions]);
    } else {
      this.questions = this.shuffleArray([...levelQuestions]).slice(0, this.NUM_QUESTIONS);
    }

    this.currentIndex = 0;
    this.userAnswers = new Array(this.questions.length).fill(null); // インデックスごとに回答を持つ

    this.switchScreen('quiz-screen');
    this.updateQuestionDisplay();
  },

  submitAnswer: function() {
    const input = document.getElementById('answer-input');
    const answer = input.value.trim();

    // 現在の問題の回答を保存（上書き）
    this.userAnswers[this.currentIndex] = {
      question: this.questions[this.currentIndex],
      userText: answer || "（無回答）"
    };

    this.currentIndex++;

    if (this.currentIndex < this.questions.length) {
      this.updateQuestionDisplay();
    } else {
      document.getElementById('progress-bar').style.width = '100%';
      this.finishQuiz();
    }
  },

  goPrevQuestion: function() {
    if (this.currentIndex === 0) {
      this.showMessage('これが最初の問題です。');
      return;
    }

    // 今の回答も保存してから戻る
    const input = document.getElementById('answer-input');
    if (input) {
      const answer = input.value.trim();
      this.userAnswers[this.currentIndex] = {
        question: this.questions[this.currentIndex],
        userText: answer || "（無回答）"
      };
    }

    this.currentIndex--;
    this.updateQuestionDisplay();
  },

  updateQuestionDisplay: function() {
    if (this.questions.length === 0) {
      this.finishQuiz();
      return;
    }

    const q = this.questions[this.currentIndex];

    // 問題番号表示
    document.getElementById('question-count').textContent =
      `Q ${this.currentIndex + 1} / ${this.questions.length}`;

    // 問題文
    document.getElementById('question-text').textContent = q.text;

    // 回答欄
    const input = document.getElementById('answer-input');
    const saved = this.userAnswers[this.currentIndex];

    if (saved && typeof saved.userText === 'string') {
      input.value = saved.userText === "（無回答）" ? "" : saved.userText;
    } else {
      input.value = "";
    }
    input.focus();

    // プログレスバー
    const progress = (this.currentIndex / this.questions.length) * 100;
    document.getElementById('progress-bar').style.width = `${progress}%`;

    // ボタン表示テキスト
    const submitBtn = document.getElementById('submit-btn');
    submitBtn.textContent =
      (this.currentIndex === this.questions.length - 1)
      ? '回答を完了する'
      : '次へ進む';
  },

  copyToClipboardFallback: function(text, inputEl, messageEl) {
    let success = false;
    const tempTextarea = inputEl;

    try {
      tempTextarea.value = text;
      tempTextarea.select();
      tempTextarea.setSelectionRange(0, 99999);

      success = document.execCommand('copy');

      tempTextarea.value = text;
      tempTextarea.selectionEnd = tempTextarea.selectionStart;
      tempTextarea.blur();

      if (success) {
        messageEl.textContent = '✅ 回答内容をコピーしました！メーラーに貼り付けて提出してください。';
      } else {
        messageEl.textContent = '❌ 自動コピーに失敗しました。上のテキストエリアの内容を全選択・コピーして提出してください。';
        tempTextarea.select();
      }

    } catch (err) {
      console.error('Copy command failed:', err);
      messageEl.textContent = '❌ 自動コピーに失敗しました。上のテキストエリアの内容を全選択・コピーして提出してください。';
      tempTextarea.select();
    }
    messageEl.classList.remove('hidden');
    return success;
  },

  finishQuiz: function() {
    const levelNames = ["", "Lv1：基礎知識", "Lv2：システム理解", "Lv3：実践応用"];
    const levelName = levelNames[this.currentLevel] || "未選択コース";
    const date = new Date().toLocaleDateString('ja-JP');

    let reportText = `【社内テスト回答提出】\n`;
    reportText += `氏名：${this.userName}\n`;
    reportText += `実施日：${date}\n`;
    reportText += `コース：${levelName}\n\n`;
    reportText += `----------------------------\n`;

    for (let i = 0; i < this.questions.length; i++) {
      const q = this.questions[i];
      const ansObj = this.userAnswers[i];
      const ansText = ansObj && typeof ansObj.userText === 'string'
        ? ansObj.userText
        : "（無回答）";

      reportText += `[Q${i + 1}] ${q.text}\n`;
      reportText += `回答：\n${ansText}\n`;
      reportText += `----------------------------\n`;
    }
    reportText += `自己評価・コメント：\n`;

    const sendTextEl = document.getElementById('send-text');
    sendTextEl.value = reportText;

    const actionBtn = document.getElementById('action-btn');
    const copyMessage = document.getElementById('copy-message');
    const subject = `【テスト回答】${this.userName} - ${levelName}`;
    const encodedBody = encodeURIComponent(reportText);

    if (encodedBody.length > this.MAILTO_LIMIT) {
      // 文字数オーバー → コピーモード
      actionBtn.textContent = '回答内容をクリップボードにコピー';
      actionBtn.className = 'btn btn-success mt-4';

      actionBtn.onclick = () => {
        if (navigator.clipboard && navigator.clipboard.writeText) {
          navigator.clipboard.writeText(reportText).then(() => {
            copyMessage.textContent = '✅ 回答内容をコピーしました！メーラーに貼り付けて提出してください。';
            copyMessage.classList.remove('hidden');
          }).catch(err => {
            console.warn('Clipboard API failed, using fallback.', err);
            this.copyToClipboardFallback(reportText, sendTextEl, copyMessage);
          });
        } else {
          this.copyToClipboardFallback(reportText, sendTextEl, copyMessage);
        }
      };

    } else {
      // mailtoでそのまま送れる
      actionBtn.textContent = 'メールアプリを起動する';
      actionBtn.className = 'btn btn-primary mt-4';
      copyMessage.classList.add('hidden');

      actionBtn.onclick = () => {
        const encodedSubject = encodeURIComponent(subject);
        window.location.href = `mailto:?subject=${encodedSubject}&body=${encodedBody}`;
      };
    }

    this.switchScreen('result-screen');
  },

  // 配列シャッフル
  shuffleArray: function(array) {
    for (let i = array.length - 1; i > 0; i--) {
      const j = Math.floor(Math.random() * (i + 1));
      [array[i], array[j]] = [array[j], array[i]];
    }
    return array;
  },

  // 画面切り替え
  switchScreen: function(screenId) {
    ['start-screen', 'quiz-screen', 'result-screen'].forEach(id => {
      const el = document.getElementById(id);
      if (!el) return;
      if (id === screenId) {
        el.classList.remove('hidden');
      } else {
        el.classList.add('hidden');
      }
    });
    window.scrollTo(0, 0);
  },

  // 簡易メッセージ
  showMessage: function(message) {
    const messageDiv = document.createElement('div');
    messageDiv.textContent = message;
    messageDiv.style.cssText =
      'position: fixed; top: 50%; left: 50%; transform: translate(-50%, -50%);' +
      'background: white; padding: 20px; border-radius: 8px;' +
      'box-shadow: 0 4px 12px rgba(0,0,0,0.2); z-index: 1000; font-weight: bold;';
    document.body.appendChild(messageDiv);
    setTimeout(() => {
      document.body.removeChild(messageDiv);
    }, 2000);
  }
};

// DOM読み込み後のイベント付け
document.addEventListener('DOMContentLoaded', () => {
  const submitBtn = document.getElementById('submit-btn');
  const prevBtn = document.getElementById('prev-btn');

  if (submitBtn) {
    submitBtn.addEventListener('click', () => window.app.submitAnswer());
  }
  if (prevBtn) {
    prevBtn.addEventListener('click', () => window.app.goPrevQuestion());
  }
});
</script>
</body>
</html>
