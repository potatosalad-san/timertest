<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>学習予定＆実績可視化アプリ</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght=300;400;500;700;900&display=swap');
        body {
            font-family: 'Noto Sans JP', sans-serif;
        }
        /* 美しいレイアウトのためのカスタムスクロールバー */
        ::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f5f9;
        }
        ::-webkit-scrollbar-thumb {
            background: #cbd5e1;
            border-radius: 3px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #94a3b8;
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 min-h-screen flex flex-col">

    <!-- ヘッダー -->
    <header class="bg-gradient-to-r from-indigo-600 to-violet-700 text-white shadow-md relative z-20">
        <div class="max-w-full mx-auto px-4 sm:px-8 py-3 flex flex-col sm:flex-row justify-between items-center gap-4">
            <div class="flex items-center gap-3">
                <div class="bg-white/20 p-2 rounded-lg backdrop-blur-sm">
                    <i data-lucide="graduation-cap" class="w-6 h-6 text-white"></i>
                </div>
                <div>
                    <p class="text-sm font-bold text-indigo-100">学習予定＆実績可視化アプリ（自動保存オン）</p>
                </div>
            </div>
            <div class="flex items-center gap-2 bg-white/10 p-1.5 rounded-lg backdrop-blur-sm relative">
                <button onclick="changeMonth(-1)" class="p-1 hover:bg-white/20 rounded transition text-white" title="前月">
                    <i data-lucide="chevron-left" class="w-5 h-5"></i>
                </button>
                <button onclick="toggleGlobalMonthPicker(event)" id="currentMonthLabelBtn" class="font-bold px-3 min-w-[100px] text-center text-sm hover:bg-white/20 py-1 rounded transition flex items-center justify-center gap-1 text-white" title="クリックして年月を直接選択">
                    <span id="currentMonthLabel">2026年6月</span>
                    <i data-lucide="calendar" class="w-3.5 h-3.5 opacity-80"></i>
                </button>
                <button onclick="changeMonth(1)" class="p-1 hover:bg-white/20 rounded transition text-white" title="翌月">
                    <i data-lucide="chevron-right" class="w-5 h-5"></i>
                </button>

                <!-- グローバル年月選択パネル -->
                <div id="globalMonthPickerPanel" class="absolute right-0 top-full mt-2 bg-white border border-slate-200 rounded-2xl shadow-2xl p-4 hidden z-50 w-64 text-slate-800">
                    <div class="space-y-4">
                        <div>
                            <label class="block text-[10px] font-black text-slate-400 mb-1">年を選択</label>
                            <select id="pickerYearSelect" class="w-full bg-slate-50 border border-slate-200 rounded-lg p-2 text-xs font-bold focus:outline-none focus:ring-2 focus:ring-indigo-500">
                                <option value="2025">2025年</option>
                                <option value="2026" selected>2026年</option>
                                <option value="2027">2027年</option>
                            </select>
                        </div>
                        <div>
                            <label class="block text-[10px] font-black text-slate-400 mb-1">月を選択</label>
                            <div class="grid grid-cols-4 gap-1.5">
                                <template id="month-picker-btn-template">
                                    <button class="month-select-btn p-1.5 text-xs font-bold rounded-lg border border-slate-100 hover:bg-indigo-50 hover:text-indigo-600 transition-colors bg-slate-50 text-slate-700 w-full"></button>
                                </template>
                                <div id="monthPickerGrid" class="grid grid-cols-4 gap-1.5 col-span-4"></div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </header>

    <!-- ナビゲーション -->
    <div class="bg-white border-b border-slate-200 sticky top-0 z-10 shadow-sm">
        <div class="max-w-full mx-auto px-4 sm:px-8">
            <nav class="flex justify-around sm:justify-start sm:gap-8 -mb-px" aria-label="Tabs">
                <button onclick="switchTab('dashboard')" id="tab-dashboard" class="tab-btn py-4 px-4 inline-flex items-center gap-2 border-b-2 border-indigo-600 font-bold text-sm text-indigo-600 transition-all duration-200">
                    <i data-lucide="bar-chart-3" class="w-5 h-5"></i>
                    <span>ダッシュボード</span>
                </button>
                <button onclick="switchTab('monthly')" id="tab-monthly" class="tab-btn py-4 px-4 inline-flex items-center gap-2 border-b-2 border-transparent font-medium text-sm text-slate-500 hover:text-slate-700 hover:border-slate-300 transition-all duration-200">
                    <i data-lucide="calendar font-medium" class="w-5 h-5"></i>
                    <span>月間進捗表</span>
                </button>
                <button onclick="switchTab('daily')" id="tab-daily" class="tab-btn py-4 px-4 inline-flex items-center gap-2 border-b-2 border-transparent font-medium text-sm text-slate-500 hover:text-slate-700 hover:border-slate-300 transition-all duration-200">
                    <i data-lucide="clock" class="w-5 h-5"></i>
                    <span>日次計画シート (Daily)</span>
                </button>
                <!-- 手帳風ウィークリービューへの切り替えタブ新設 -->
                <button onclick="switchTab('weekly')" id="tab-weekly" class="tab-btn py-4 px-4 inline-flex items-center gap-2 border-b-2 border-transparent font-medium text-sm text-slate-500 hover:text-slate-700 hover:border-slate-300 transition-all duration-200">
                    <i data-lucide="book-open" class="w-5 h-5 text-indigo-500 animate-pulse"></i>
                    <span class="font-bold">週間計画シート (Weekly)</span>
                </button>
                <button onclick="switchTab('timer')" id="tab-timer" class="tab-btn py-4 px-4 inline-flex items-center gap-2 border-b-2 border-transparent font-medium text-sm text-slate-500 hover:text-slate-700 hover:border-slate-300 transition-all duration-200">
                    <i data-lucide="timer" class="w-5 h-5"></i>
                    <span>学習タイマー</span>
                </button>
            </nav>
        </div>
    </div>

    <!-- メインコンテンツ -->
    <main class="flex-grow max-w-full w-full mx-auto p-4 sm:p-8">
        
        <!-- ダッシュボードタブ -->
        <section id="content-dashboard" class="tab-content space-y-6">
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">
                <div class="bg-white p-5 rounded-2xl border border-slate-100 shadow-sm flex items-center gap-4">
                    <div class="p-3 bg-indigo-50 text-indigo-600 rounded-xl">
                        <i data-lucide="clock" class="w-6 h-6"></i>
                    </div>
                    <div>
                        <p class="text-xs text-slate-400 font-medium">今月の総学習時間</p>
                        <h3 class="text-2xl font-bold mt-1 text-slate-800" id="stat-total-time">0時間</h3>
                    </div>
                </div>
                <div class="bg-white p-5 rounded-2xl border border-slate-100 shadow-sm flex items-center gap-4">
                    <div class="p-3 bg-emerald-50 text-emerald-600 rounded-xl">
                        <i data-lucide="calendar-check" class="w-6 h-6"></i>
                    </div>
                    <div>
                        <p class="text-xs text-slate-400 font-medium">学習を記録した日数</p>
                        <h3 class="text-2xl font-bold mt-1 text-slate-800" id="stat-active-days">0日</h3>
                    </div>
                </div>
                <div class="bg-white p-5 rounded-2xl border border-slate-100 shadow-sm flex items-center gap-4">
                    <div class="p-3 bg-amber-50 text-amber-600 rounded-xl">
                        <i data-lucide="target" class="w-6 h-6"></i>
                    </div>
                    <div>
                        <p class="text-xs text-slate-400 font-medium">今日の予定達成率</p>
                        <h3 class="text-2xl font-bold mt-1 text-slate-800" id="stat-today-completion">0%</h3>
                    </div>
                </div>
                <div class="bg-white p-5 rounded-2xl border border-slate-100 shadow-sm flex items-center gap-4">
                    <div class="p-3 bg-violet-50 text-violet-600 rounded-xl">
                        <i data-lucide="book-open" class="w-6 h-6"></i>
                    </div>
                    <div>
                        <p class="text-xs text-slate-400 font-medium">登録教科数</p>
                        <h3 class="text-2xl font-bold mt-1 text-slate-800" id="stat-subjects-count">2教科</h3>
                    </div>
                </div>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
                <div class="bg-white p-6 rounded-2xl border border-slate-100 shadow-sm lg:col-span-1">
                    <div class="flex justify-between items-center mb-4">
                        <h4 class="text-base font-bold text-slate-800 flex items-center gap-2">
                            <i data-lucide="pie-chart" class="w-5 h-5 text-indigo-500"></i>
                            教科別学習バランス (時間/分)
                        </h4>
                    </div>
                    <div class="relative h-64 flex items-center justify-center">
                        <canvas id="subjectPieChart"></canvas>
                    </div>
                </div>

                <div class="bg-white p-6 rounded-2xl border border-slate-100 shadow-sm lg:col-span-2">
                    <div class="flex flex-col sm:flex-row justify-between sm:items-center gap-2 mb-4">
                        <h4 class="text-base font-bold text-slate-800 flex items-center gap-2">
                            <i data-lucide="trending-up" class="w-5 h-5 text-indigo-500"></i>
                            学習時間の推移（分）
                        </h4>
                        <div class="inline-flex bg-slate-100 p-1 rounded-xl">
                            <button onclick="setTrendViewMode('week')" id="trendModeWeek" class="px-3 py-1.5 text-xs font-bold rounded-lg text-slate-500 hover:text-slate-700 transition-all">
                                週別表示
                            </button>
                            <button onclick="setTrendViewMode('month')" id="trendModeMonth" class="px-3 py-1.5 text-xs font-bold rounded-lg bg-white text-slate-800 shadow-sm transition-all">
                                月別表示
                            </button>
                            <button onclick="setTrendViewMode('year')" id="trendModeYear" class="px-3 py-1.5 text-xs font-bold rounded-lg text-slate-500 hover:text-slate-700 transition-all">
                                年間表示
                            </button>
                        </div>
                    </div>
                    <div class="relative h-60">
                        <canvas id="dailyTrendChart"></canvas>
                    </div>
                </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <div class="bg-white p-6 rounded-2xl border border-slate-100 shadow-sm">
                    <div class="flex justify-between items-center mb-4">
                        <h4 class="text-base font-bold text-slate-800 flex items-center gap-2">
                            <i data-lucide="bookmark" class="w-5 h-5 text-indigo-500"></i>
                            登録中の学習教科
                        </h4>
                        <span class="text-xs text-slate-400">※丸い色の部分をクリックして色を変えられます</span>
                    </div>
                    <div id="dashboardSubjectsList" class="space-y-3 max-h-60 overflow-y-auto pr-1"></div>
                </div>

                <div class="bg-white p-6 rounded-2xl border border-slate-100 shadow-sm flex flex-col justify-between">
                    <div>
                        <h4 class="text-base font-bold text-slate-800 mb-3 flex items-center gap-2">
                            <i data-lucide="sparkles" class="w-5 h-5 text-amber-500"></i>
                            学習アシスト＆Tips
                        </h4>
                        <div class="p-4 bg-gradient-to-br from-indigo-50 to-pink-50 rounded-xl border border-indigo-100/50 mb-4">
                            <p class="text-sm text-slate-700 leading-relaxed font-medium" id="dashboardTips">
                                タイムラインでお好みの「ブラシ（教科）」を選択して、マスを塗るだけ！簡単にカラフルな予定＆実績表が作れます。
                            </p>
                        </div>
                    </div>
                    <div class="flex items-center justify-between border-t border-slate-100 pt-4 text-xs text-slate-500">
                        <span>学習アドバイザーAI推奨</span>
                        <button onclick="generateNewTip()" class="text-indigo-600 hover:text-indigo-700 font-bold flex items-center gap-1">
                            <i data-lucide="refresh-cw" class="w-3.5 h-3.5"></i>
                            別のアドバイス
                        </button>
                    </div>
                </div>
            </div>
        </section>

        <!-- 月間進捗データタブ -->
        <section id="content-monthly" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-100 shadow-sm">
                <div class="flex flex-col md:flex-row justify-between items-start md:items-center gap-4 mb-6">
                    <div>
                        <h2 class="text-lg font-black text-slate-800 flex items-center gap-2" id="monthlyTitle">
                            <i data-lucide="calendar" class="w-5 h-5 text-indigo-500"></i>
                            n月の学習進捗表
                        </h2>
                        <p class="text-xs text-slate-500 mt-1 font-medium">日付ごとに「実際に何をしたか（文字）」を入力してください。自動で即時保存されます。すべての教科の見出し右側にある「×」印から教科を削除できます。</p>
                    </div>
                    <div class="flex flex-wrap items-center gap-2">
                        <button onclick="openAddSubjectModal()" class="bg-indigo-600 hover:bg-indigo-700 text-white px-3 py-2 rounded-xl transition-colors flex items-center gap-1.5 text-xs font-bold shadow-sm">
                            <i data-lucide="plus-circle" class="w-4 h-4"></i>
                            教科を追加
                        </button>
                    </div>
                </div>

                <div class="overflow-x-auto border border-slate-200 rounded-xl shadow-inner bg-slate-50/50">
                    <table class="w-full text-center border-collapse min-w-[700px]">
                        <thead>
                            <tr class="bg-slate-100 border-b border-slate-300">
                                <th class="py-3.5 px-4 text-xs font-black text-slate-600 w-20 border-r border-slate-200">日</th>
                                <th id="customHeadersContainer" class="p-0 border-r border-slate-200" style="display: contents;"></th>
                                <th class="py-3.5 px-4 text-xs font-semibold text-slate-600 w-52 bg-slate-50">
                                    <span class="text-xs block font-bold text-slate-700">任意メモ・トピック</span>
                                    <span class="text-[9px] text-slate-400 block font-normal">(予定や日記代わりに自由に記入できます)</span>
                                </th>
                            </tr>
                        </thead>
                        <tbody id="monthlyTableBody" class="divide-y divide-slate-200 text-slate-700 bg-white"></tbody>
                    </table>
                </div>
            </div>
        </section>

        <!-- 日次計画シートタブ -->
        <section id="content-daily" class="tab-content hidden space-y-6">
            <div class="bg-white p-6 rounded-2xl border border-slate-100 shadow-sm">
                <div class="flex flex-col md:flex-row justify-between items-start md:items-center gap-4 mb-6">
                    <div>
                        <h2 class="text-lg font-black text-slate-800 flex items-center gap-2">
                            <i data-lucide="clock" class="w-5 h-5 text-indigo-500"></i>
                            日次計画＆バーチカル時間記録 (Daily)
                        </h2>
                        <p class="text-xs text-slate-500 mt-1">手書きのスケジュール手帳のように「予定」と「記録」を縦に並べて塗りつぶし管理できます。週間計画シート側と完全にリアルタイム同期します。</p>
                    </div>
                    <div class="flex items-center gap-3">
                        <div class="flex items-center gap-1 bg-slate-100 p-1 rounded-xl border border-slate-200">
                            <button onclick="navigateDailyDay(-1)" class="p-1.5 hover:bg-white rounded-lg transition text-slate-700" title="前日に戻る">
                                <i data-lucide="chevron-left" class="w-4 h-4"></i>
                            </button>

                            <div class="relative">
                                <button id="dailyCalendarBtn" onclick="toggleDailyCalendarPopup(event)" class="bg-white border border-slate-250 hover:bg-slate-50 text-slate-700 rounded-lg px-3 py-1.5 text-xs font-bold flex items-center gap-1.5 transition-all shadow-sm">
                                    <i data-lucide="calendar" class="w-3.5 h-3.5 text-indigo-600"></i>
                                    <span id="selectedDayLabel">15日</span>
                                    <i data-lucide="chevron-down" class="w-3 h-3 text-slate-400"></i>
                                </button>

                                <div id="dailyCalendarDropdown" class="absolute right-1/2 translate-x-1/2 md:translate-x-0 md:right-0 top-full mt-2 bg-white border border-slate-200 rounded-2xl shadow-2xl p-4 hidden z-50 w-72 text-slate-800">
                                    <div class="flex justify-between items-center mb-3">
                                        <button onclick="navigateCalendarMonth(-1, event)" class="p-1 hover:bg-slate-100 rounded transition" title="前月へ">
                                            <i data-lucide="chevron-left" class="w-4 h-4"></i>
                                        </button>
                                        <span id="calendarDropdownMonthLabel" class="font-black text-xs text-slate-800">2026年6月</span>
                                        <button onclick="navigateCalendarMonth(1, event)" class="p-1 hover:bg-slate-100 rounded transition" title="翌月へ">
                                            <i data-lucide="chevron-right" class="w-4 h-4"></i>
                                        </button>
                                    </div>
                                    <div class="grid grid-cols-7 gap-1 text-center text-[10px] font-black text-slate-400 mb-1 border-b border-slate-100 pb-1">
                                        <div class="text-rose-500">日</div><div>月</div><div>火</div><div>水</div><div>木</div><div>金</div><div class="text-sky-500">土</div>
                                    </div>
                                    <div id="calendarGridContainer" class="grid grid-cols-7 gap-1 text-center"></div>
                                    <div class="mt-3 pt-2 border-t border-slate-100 flex justify-between items-center text-[9px] text-slate-400">
                                        <span class="text-emerald-600 font-bold bg-emerald-50 border border-emerald-100 px-2 py-0.5 rounded-full" id="calendarTodayIndicator">今日: 28日</span>
                                        <button onclick="jumpToTodayInCalendar(event)" class="text-indigo-600 hover:underline font-bold">今日に戻る</button>
                                    </div>
                                </div>
                            </div>

                            <button onclick="navigateDailyDay(1)" class="p-1.5 hover:bg-white rounded-lg transition text-slate-700" title="翌日に進む">
                                <i data-lucide="chevron-right" class="w-4 h-4"></i>
                            </button>
                        </div>
                    </div>
                </div>

                <div class="border border-slate-300 rounded-xl p-4 sm:p-6 bg-amber-50/20 space-y-6 max-w-full mx-auto">
                    <div class="border-2 border-slate-800 bg-white rounded-lg shadow-sm overflow-hidden text-xs">
                        
                        <div class="grid grid-cols-1 md:grid-cols-12 border-b-2 border-slate-800">
                            <div class="md:col-span-2 bg-slate-800 text-white font-black text-center py-4 flex flex-col justify-center items-center">
                                <span class="text-xl" id="dailyLogDateLabel">15日</span>
                                <span class="text-[10px]" id="dailyLogWeekDayLabel">(月)</span>
                            </div>
                            <div class="md:col-span-10 grid grid-cols-2 sm:grid-cols-3 divide-x divide-slate-800 bg-slate-50 text-slate-700">
                                <div class="p-3 flex flex-col justify-center items-center">
                                    <span class="text-[10px] text-slate-400 font-bold block mb-1">今日の計画学習時間</span>
                                    <div class="flex items-baseline gap-1">
                                        <input type="number" id="dailyPlannedTotal" placeholder="0" class="w-12 text-center font-bold text-base bg-transparent border-b border-indigo-300 focus:outline-none text-indigo-700" onchange="calculateDailySummary(); saveAllData(true);">
                                        <span class="font-bold text-xs">時間</span>
                                    </div>
                                </div>
                                <div class="p-3 flex flex-col justify-center items-center">
                                    <span class="text-[10px] text-emerald-600 font-bold block mb-1">今日の実績学習時間</span>
                                    <div class="flex items-baseline gap-1 text-emerald-700">
                                        <span id="dailyActualTotal" class="text-base font-extrabold">0.0</span>
                                        <span class="font-bold text-xs">時間</span>
                                    </div>
                                </div>
                                <div class="p-3 col-span-2 sm:col-span-1 flex flex-col justify-center items-center bg-indigo-50/50">
                                    <span class="text-[10px] text-indigo-700 font-bold block mb-1">今日の合計実績（分）</span>
                                    <div class="flex items-baseline gap-1 text-indigo-800 font-extrabold">
                                        <span id="dailyCumulativeTotal" class="text-lg">0</span>
                                        <span class="font-bold text-xs">分</span>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- 塗りつぶし用ブラシの選択パレット -->
                        <div class="p-4 bg-slate-50 border-b-2 border-slate-800">
                            <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center gap-3">
                                <div class="flex items-center gap-2">
                                    <i data-lucide="palette" class="w-4 h-4 text-indigo-600 animate-pulse"></i>
                                    <span class="font-black text-xs text-slate-700">塗りつぶし用ブラシ(教科)を選択:</span>
                                </div>
                                <div class="text-[10px] text-slate-400 font-medium">使い方: 教科(ブラシ)を選んで下の縦型スケジュール表の予定や記録エリアをタップして色を塗ります。</div>
                            </div>
                            <div id="brushPaletteContainer" class="flex flex-wrap gap-2 mt-2.5"></div>
                        </div>

                        <!-- タイムライン表レイアウト (縦表示) -->
                        <div class="bg-slate-100 overflow-hidden">
                            <!-- ヘッダー -->
                            <div class="grid grid-cols-12 bg-slate-200 border-b-2 border-slate-800 text-center font-bold py-2 select-none text-[11px] text-slate-700">
                                <div class="col-span-3 border-r border-slate-300">時間帯</div>
                                <div class="col-span-4 border-r border-slate-300 text-indigo-600 flex items-center justify-center gap-1">
                                    <i data-lucide="calendar-days" class="w-3.5 h-3.5"></i>予定 (Plan)
                                </div>
                                <div class="col-span-5 text-emerald-700 flex items-center justify-center gap-1">
                                    <i data-lucide="check-circle-2" class="w-3.5 h-3.5"></i>実績 (Actual)
                                </div>
                            </div>
                            <!-- スクロール可能なスケジュール本体 -->
                            <div id="dynamicTimelinesContainer" class="divide-y divide-slate-300 max-h-[500px] overflow-y-auto bg-white"></div>
                        </div>

                        <div class="grid grid-cols-1 lg:grid-cols-12 divide-y lg:divide-y-0 lg:divide-x divide-slate-800">
                            <div class="lg:col-span-8 p-4 space-y-4">
                                <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center gap-2 border-b border-slate-200 pb-2 mb-3">
                                    <div>
                                        <h5 class="font-bold text-slate-700 flex items-center gap-1.5">
                                            <i data-lucide="list-todo" class="w-4 h-4 text-indigo-500"></i>
                                            教科ごとの計画＆実績内容・学習時間
                                        </h5>
                                        <p class="text-[10px] text-slate-400 mt-0.5">※教科の丸（●）をクリックするとその教科の色を選べます</p>
                                    </div>
                                    <!-- 新規教科をポップアップ入力へ誘導するボタン -->
                                    <button onclick="openAddSubjectModal()" class="bg-indigo-600 hover:bg-indigo-700 text-white px-2.5 py-1.5 rounded-lg transition-colors flex items-center gap-1 text-[10px] font-bold">
                                        <i data-lucide="plus" class="w-3.5 h-3.5"></i>
                                        教科を追加
                                    </button>
                                </div>
                                <div id="dailySubjectsContainer" class="space-y-4 max-h-[400px] overflow-y-auto pr-1"></div>
                            </div>

                            <div class="lg:col-span-4 p-4 flex flex-col justify-between space-y-4">
                                <div class="space-y-3">
                                    <h5 class="font-bold text-slate-700 flex items-center gap-1.5 border-b border-slate-200 pb-2">
                                        <i data-lucide="message-square" class="w-4 h-4 text-emerald-500"></i>
                                        今日の反省・一言メモ
                                    </h5>
                                    <textarea id="dailyReflection" rows="6" placeholder="（例）今日は集中して数学を進めることができた。計画通りにできなかった英語は明日の朝一番に実施する。" class="w-full p-2.5 bg-amber-50/10 border border-slate-200 rounded-lg text-xs leading-relaxed focus:bg-white focus:ring-1 focus:ring-emerald-500 focus:outline-none resize-none" onchange="saveAllData(true);"></textarea>
                                </div>

                                <div class="bg-slate-50 p-3 rounded-lg border border-slate-100 space-y-2">
                                    <span class="font-bold text-slate-600 block text-[10px]">今日の自己評価:</span>
                                    <div class="flex items-center gap-3 justify-center">
                                        <button onclick="setEvaluation(3)" id="evalBtn3" class="eval-btn flex flex-col items-center p-2 rounded-lg bg-white border border-slate-200 hover:border-indigo-400 w-16 transition-all">
                                            <span class="text-lg">😆</span>
                                            <span class="text-[9px] mt-1 font-bold text-slate-500">バッチリ</span>
                                        </button>
                                        <button onclick="setEvaluation(2)" id="evalBtn2" class="eval-btn flex flex-col items-center p-2 rounded-lg bg-white border border-slate-200 hover:border-indigo-400 w-16 transition-all">
                                            <span class="text-lg">🙂</span>
                                            <span class="text-[9px] mt-1 font-bold text-slate-500">まずまず</span>
                                        </button>
                                        <button onclick="setEvaluation(1)" id="evalBtn1" class="eval-btn flex flex-col items-center p-2 rounded-lg bg-white border border-slate-200 hover:border-indigo-400 w-16 transition-all">
                                            <span class="text-lg">😞</span>
                                            <span class="text-[9px] mt-1 font-bold text-slate-500">がんばろう</span>
                                        </button>
                                    </div>
                                </div>
                            </div>
                        </div>

                    </div>
                </div>
            </div>
        </section>

        <!-- 週間計画シートタブ -->
        <section id="content-weekly" class="tab-content hidden space-y-6">
            <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center gap-4">
                <div>
                    <h2 class="text-lg font-black text-slate-800 flex items-center gap-2">
                        <i data-lucide="book-open" class="w-5 h-5 text-indigo-500"></i>
                        週間学習手帳ビュー (Weekly)
                    </h2>
                    <p class="text-xs text-slate-500 mt-0.5">アップロード画像と同じルーズリーフ見開き設計。1週間のTODO、目標、時間帯（6:00〜24:00）をひと目で確認・編集できます。</p>
                </div>
                <!-- 週間ナビゲーション -->
                <div class="flex items-center gap-2 bg-slate-100 p-1 rounded-xl border">
                    <button onclick="navigateWeeklyWeek(-1)" class="p-1.5 hover:bg-white rounded-lg transition text-slate-700" title="前週へ">
                        <i data-lucide="chevron-left" class="w-4 h-4"></i>
                    </button>
                    <span id="weeklyWeekRangeLabel" class="font-bold text-xs text-slate-700 px-3">2026/6/15 〜 6/21</span>
                    <button onclick="navigateWeeklyWeek(1)" class="p-1.5 hover:bg-white rounded-lg transition text-slate-700" title="翌週へ">
                        <i data-lucide="chevron-right" class="w-4 h-4"></i>
                    </button>
                </div>
            </div>

            <!-- ブラシパレット選択（手帳タイムライン色塗りのために共有配置） -->
            <div class="bg-white border rounded-2xl p-4 shadow-sm space-y-2">
                <div class="flex items-center justify-between">
                    <span class="text-xs font-bold text-slate-700 flex items-center gap-1">
                        <i data-lucide="brush" class="w-4 h-4 text-indigo-500 animate-bounce"></i>
                        タイムライン塗り用ブラシ：
                    </span>
                    <span class="text-[10px] text-slate-400">※曜日カードの「P」列（予定）や「A」列（記録）のブロックをクリックしてパチポチ塗れます</span>
                </div>
                <div id="weeklyBrushPaletteContainer" class="flex flex-wrap gap-2"></div>
            </div>

            <!-- 手帳見開きコンテナ -->
            <div class="bg-sky-50/30 rounded-3xl p-4 sm:p-6 border border-slate-200 shadow-lg relative max-w-full">
                <!-- ルーズリーフデザイン -->
                <div class="bg-white rounded-2xl border border-slate-200 shadow-xl overflow-hidden relative">
                    
                    <div class="grid grid-cols-1 xl:grid-cols-2 bg-[#fdfdfd] divide-y xl:divide-y-0 xl:divide-x divide-slate-200 p-4 sm:p-6 relative">
                        
                        <!-- 中央バインダーリング (XL以上の見開き表示時のみ装飾表示) -->
                        <div id="binderRingsContainer" class="hidden xl:flex flex-col justify-between items-center absolute top-4 bottom-4 left-1/2 -translate-x-1/2 z-20 w-8 h-[95%] py-4 pointer-events-none">
                            <!-- JSでリングパーツが動的に挿入されます -->
                        </div>

                        <!-- ================= 左ページ ================= -->
                        <div class="xl:pr-8 space-y-6">
                            
                            <!-- 11月のインデックスとWEEKLY GOAL、週間総学習時間 -->
                            <div class="grid grid-cols-12 gap-3 items-center border-b pb-4">
                                <div class="col-span-3 bg-indigo-50 border border-indigo-100 rounded-xl py-2 px-1 text-center">
                                    <span class="text-2xl font-black text-indigo-600 font-mono" id="weeklyPageMonthLabel">6</span>
                                    <span class="text-xs font-bold text-indigo-500 block">MONTH</span>
                                </div>
                                <div class="col-span-9 space-y-1">
                                    <span class="text-[10px] font-black text-slate-400 tracking-wider">WEEKLY GOAL</span>
                                    <input type="text" id="weeklyGoalInput" onchange="appData.weeklyGoals[currentWeekKey] = this.value; saveAllData(true);" placeholder="（例）模擬テストに向けて苦手科目に集中！" class="w-full bg-slate-50 border border-slate-200 rounded-lg p-2 text-xs font-bold focus:outline-none focus:bg-white focus:ring-1 focus:ring-indigo-500 text-slate-700">
                                </div>
                            </div>

                            <!-- WEEKLY TO DO（今週やることリスト） -->
                            <div class="bg-slate-50/70 p-4 rounded-xl border border-slate-200/60 space-y-3">
                                <div class="flex justify-between items-center border-b pb-1.5">
                                    <span class="text-xs font-black text-slate-500 tracking-wider flex items-center gap-1">
                                        <i data-lucide="check-square" class="w-4 h-4 text-indigo-500"></i>
                                        WEEKLY TO DO
                                    </span>
                                    <button onclick="addWeeklyToDo()" class="text-indigo-600 hover:text-indigo-700 font-bold text-[10px] flex items-center gap-0.5">
                                        <i data-lucide="plus-circle" class="w-3 h-3"></i>追加
                                    </button>
                                </div>
                                <div id="weeklyToDoContainer" class="space-y-2 max-h-48 overflow-y-auto pr-1">
                                    <!-- 動的にToDoを追加表示 -->
                                </div>
                            </div>

                            <!-- 月曜日・火曜日・水曜日 -->
                            <div class="grid grid-cols-1 md:grid-cols-3 gap-4" id="weeklyLeftDaysContainer"></div>
                        </div>

                        <!-- ================= 右ページ ================= -->
                        <div class="xl:pl-8 space-y-6 pt-6 xl:pt-0">
                            
                            <!-- WEEK IN REVIEW と WEEKLY TOTAL -->
                            <div class="grid grid-cols-12 gap-3 items-center border-b pb-4">
                                <div class="col-span-7 space-y-1">
                                    <span class="text-[10px] font-black text-slate-400 tracking-wider">WEEK IN REVIEW (ふりかえり・メモ)</span>
                                    <input type="text" id="weeklyReviewInput" onchange="appData.weeklyReviews[currentWeekKey] = this.value; saveAllData(true);" placeholder="（例）文法の振り返りをして理解度が深まった！" class="w-full bg-slate-50 border border-slate-200 rounded-lg p-2 text-xs font-bold focus:outline-none focus:bg-white focus:ring-1 focus:ring-emerald-500 text-slate-700">
                                </div>
                                <div class="col-span-5 bg-emerald-50 border border-emerald-100 rounded-xl py-2 px-1 text-center">
                                    <span class="text-lg font-black text-emerald-700 font-mono block" id="weeklyTotalTimeLabel">00h 00m</span>
                                    <span class="text-[9px] font-bold text-emerald-500 block">WEEKLY TOTAL</span>
                                </div>
                            </div>

                            <!-- 木曜日・金曜日・土曜日・日曜日 -->
                            <div class="grid grid-cols-1 md:grid-cols-4 xl:grid-cols-4 gap-4" id="weeklyRightDaysContainer"></div>
                        </div>

                    </div>
                </div>
            </div>
        </section>

        <!-- タイマータブ -->
        <section id="content-timer" class="tab-content hidden space-y-6">
            <div class="grid grid-cols-1 md:grid-cols-12 gap-6 max-w-full mx-auto">
                
                <!-- 左側コントロールパネル -->
                <div class="md:col-span-5 space-y-4">
                    
                    <!-- ポモドーロサイクル設定 -->
                    <div class="bg-gradient-to-br from-indigo-50 to-purple-50 rounded-2xl border border-indigo-100 shadow-sm p-4 space-y-3">
                        <div class="flex justify-between items-center">
                            <span class="text-xs font-black text-indigo-800 flex items-center gap-1.5">
                                <i data-lucide="brain" class="w-4 h-4 text-pink-500 animate-pulse"></i>
                                ポモドーロ・サイクル設定
                            </span>
                            <span class="text-[9px] bg-indigo-100 text-indigo-700 px-2 py-0.5 rounded-full font-bold">効率UPモード</span>
                        </div>
                        <p class="text-[10px] text-slate-500 leading-normal">
                            25分の集中と5分の休憩を繰り返します。自動ループをONにすると、記録完了後に次のタイマーが自動で始まります。
                        </p>
                        
                        <!-- ポモドーロ一発簡単セットボタン -->
                        <button onclick="setPomodoroTechnique()" class="w-full bg-indigo-600 hover:bg-indigo-700 text-white py-2 px-3 rounded-xl font-bold text-xs flex items-center justify-center gap-2 transition-all shadow-sm">
                            <i data-lucide="sparkles" class="w-4 h-4"></i>
                            ポモドーロテクニックを即時セット (25分集中+ループON)
                        </button>
                        
                        <!-- 自動ループ切り替えトグル -->
                        <div class="flex items-center justify-between bg-white/60 p-2 rounded-xl border border-indigo-100/50">
                            <span class="text-xs font-bold text-slate-700 flex items-center gap-1">
                                <i data-lucide="refresh-cw" class="w-3.5 h-3.5 text-indigo-600"></i>
                                集中と休憩を自動ループする
                            </span>
                            <label class="relative inline-flex items-center cursor-pointer">
                                <input type="checkbox" id="pomodoroAutoLoopToggle" onchange="toggleAutoLoopSetting(this.checked)" class="sr-only peer">
                                <div class="w-9 h-5 bg-slate-200 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-slate-300 after:border after:rounded-full after:h-4 after:w-4 after:transition-all peer-checked:bg-indigo-600"></div>
                            </label>
                        </div>

                        <div class="grid grid-cols-2 gap-2">
                            <button onclick="selectPomodoroCycle('focus')" class="py-2.5 px-3 rounded-xl border border-indigo-200 bg-white text-indigo-700 hover:bg-indigo-50 font-bold text-xs flex flex-col items-center gap-1 shadow-sm transition-all hover:scale-[1.02]">
                                <span class="text-base">🧠</span>
                                <span>25分集中セット</span>
                            </button>
                            <button onclick="selectPomodoroCycle('break')" class="py-2.5 px-3 rounded-xl border border-emerald-200 bg-white text-emerald-700 hover:bg-emerald-50 font-bold text-xs flex flex-col items-center gap-1 shadow-sm transition-all hover:scale-[1.02]">
                                <span class="text-base">☕</span>
                                <span>5分休憩セット</span>
                            </button>
                        </div>
                    </div>

                    <div class="bg-slate-200 p-1 rounded-xl flex">
                        <button onclick="setTimerStateMode('focus')" id="timerModeFocusBtn" class="flex-grow py-2 text-xs font-black rounded-lg bg-indigo-600 text-white shadow-sm transition-all">
                            集中する
                        </button>
                        <button onclick="setTimerStateMode('break')" id="timerModeBreakBtn" class="flex-grow py-2 text-xs font-bold rounded-lg text-slate-600 hover:text-slate-800 transition-all">
                            休憩する
                        </button>
                    </div>

                    <!-- マイタイマー -->
                    <div class="bg-white rounded-2xl border border-slate-200 shadow-sm p-4 space-y-3">
                        <div class="flex justify-between items-center border-b border-slate-100 pb-2">
                            <span class="text-[10px] font-black text-slate-400 uppercase tracking-wider flex items-center gap-1" id="timerSlotsTitleLabel">
                                <i data-lucide="star" class="w-3.5 h-3.5 text-amber-400 fill-amber-400"></i>
                                マイタイマー (集中 5枠)
                            </span>
                        </div>
                        <div id="customTimerSlotsContainer" class="space-y-3"></div>
                    </div>

                    <!-- 分類選択 -->
                    <div class="bg-white rounded-2xl border border-slate-200 shadow-sm p-4 space-y-2">
                        <div class="flex justify-between items-center mb-2">
                            <span class="text-[10px] font-black text-slate-400 uppercase tracking-wider">集中することの分類</span>
                            <div class="flex items-center gap-1.5">
                                <button onclick="openAddSubjectModal()" class="text-slate-400 hover:text-indigo-600 p-1 transition-colors" title="新しい教科・分類を追加">
                                    <i data-lucide="plus" class="w-4 h-4"></i>
                                </button>
                            </div>
                        </div>
                        <div id="classificationListContainer" class="space-y-1 max-h-56 overflow-y-auto pr-1"></div>
                    </div>
                </div>

                <!-- 右側タイマー表示 -->
                <div class="md:col-span-7 flex flex-col justify-between bg-white rounded-2xl border border-slate-200 shadow-sm p-6 space-y-6">
                    <div class="space-y-4">
                        <div class="bg-slate-50 p-4 rounded-xl border border-slate-100 flex flex-col items-center justify-center space-y-1 text-center">
                            <span class="text-slate-400 text-[10px] font-bold">現在の選択状態</span>
                            <div class="flex items-center gap-1.5 text-base font-black text-slate-800">
                                <span id="summaryModeLabel" class="text-indigo-600">集中 [25分]</span>
                                <span class="text-slate-300">|</span>
                                <span id="summarySubjectLabel">国語</span>
                            </div>
                        </div>

                        <div class="p-6 bg-slate-900 text-white rounded-2xl text-center space-y-2 shadow-inner relative">
                            <span id="bigTimerTitle" class="block text-[10px] font-black text-indigo-400 uppercase tracking-wider">READY TO STUDY</span>
                            <span id="bigTimerDisplay" class="font-mono text-5xl sm:text-6xl font-black tracking-widest text-slate-100 select-none block">25:00</span>
                            <div id="mainTimerOvertimeLabel" class="text-rose-500 font-bold text-xs mt-1 hidden animate-pulse">※制限時間を超過して自習時間を記録中！</div>
                        </div>
                    </div>

                    <button onclick="startFullscreenTimer()" class="w-full bg-indigo-600 hover:bg-indigo-700 text-white py-4 rounded-xl text-sm font-black transition-all shadow-lg shadow-indigo-600/20 active:scale-95 flex items-center justify-center gap-2">
                        <i data-lucide="play" class="w-5 h-5"></i>
                        タイマーをスタート（全画面表示）
                    </button>
                </div>
            </div>
        </section>

    </main>

    <!-- フルスクリーンタイマー -->
    <div id="fullscreenTimerOverlay" class="fixed inset-0 bg-slate-950 z-50 flex flex-col justify-between p-6 sm:p-10 hidden transition-all select-none">
        <div class="flex justify-between items-center">
            <div class="flex items-center gap-2">
                <span id="fullscreenDotIndicator" class="w-2.5 h-2.5 rounded-full bg-emerald-500 animate-pulse"></span>
                <span id="fullscreenSubjectLabel" class="text-xs font-black text-slate-400 tracking-wider">国語 集中時間</span>
            </div>
            <button onclick="quitFullscreenTimerConfirm()" class="p-2 text-slate-400 hover:text-white bg-slate-900 border border-slate-800 rounded-full transition-all active:scale-95">
                <i data-lucide="x" class="w-5 h-5"></i>
            </button>
        </div>

        <div class="flex flex-col items-center justify-center space-y-6">
            <div class="relative w-64 h-64 sm:w-80 sm:h-80 flex items-center justify-center">
                <svg class="absolute inset-0 w-full h-full transform -rotate-90">
                    <circle cx="50%" cy="50%" r="44%" class="stroke-slate-900" stroke-width="4" fill="transparent" />
                    <circle id="fullscreenProgressRing" cx="50%" cy="50%" r="44%" class="stroke-indigo-500 transition-all duration-300" stroke-width="6" fill="transparent" stroke-linecap="round" stroke-dasharray="1000" stroke-dashoffset="0" />
                </svg>

                <div class="text-center space-y-1">
                    <span id="fullscreenDigits" class="font-mono text-5xl sm:text-6xl font-black text-slate-100 tracking-widest block">25:00</span>
                    <span id="fullscreenPercentage" class="text-[10px] font-black text-slate-500 block">100% REMAINING</span>
                </div>
            </div>
            <p id="fullscreenInspiringMessage" class="text-slate-400 text-xs text-center max-w-sm font-medium leading-relaxed">
                スマートフォンを裏返して、自分だけの特別な勉強時間に集中しましょう。
            </p>
        </div>

        <div class="flex items-center justify-center gap-4">
            <button onclick="resetFullscreenTimer()" class="p-3 bg-slate-900 hover:bg-slate-800 text-slate-300 rounded-full transition-all border border-slate-800 active:scale-95">
                <i data-lucide="rotate-ccw" class="w-5 h-5"></i>
            </button>
            <button onclick="toggleFullscreenTimer()" id="fullscreenPlayBtn" class="p-4 bg-indigo-600 hover:bg-indigo-500 text-white rounded-full transition-all shadow-xl shadow-indigo-600/30 active:scale-95">
                <i data-lucide="pause" class="w-6 h-6" id="fullscreenPlayIcon"></i>
            </button>
            <button onclick="forceCompleteTimerConfirm()" class="p-3 bg-slate-900 hover:bg-slate-800 text-slate-300 rounded-full transition-all border border-slate-800 active:scale-95">
                <i data-lucide="check" class="w-5 h-5"></i>
            </button>
        </div>
    </div>

    <!-- 教科追加用ポップアップモーダル -->
    <div id="addSubjectModal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm flex items-center justify-center hidden z-[110] p-4">
        <div class="bg-white rounded-2xl p-6 max-w-sm w-full shadow-2xl border border-slate-100 space-y-4 transform scale-95 transition-all">
            <div class="flex items-center gap-3 text-indigo-600">
                <div class="p-2 bg-indigo-50 rounded-lg">
                    <i data-lucide="bookmark-plus" class="w-6 h-6"></i>
                </div>
                <h4 class="text-base font-black text-slate-800">新規教科を追加</h4>
            </div>
            
            <div class="space-y-3">
                <div>
                    <label class="block text-[11px] font-bold text-slate-500 mb-1">教科名 / カテゴリ名</label>
                    <input type="text" id="modalSubjectNameInput" placeholder="例: 英語、世界史、基本情報" class="w-full bg-slate-50 border border-slate-200 rounded-xl p-3 text-xs font-bold focus:outline-none focus:ring-2 focus:ring-indigo-500 text-slate-700">
                </div>
                <div>
                    <label class="block text-[11px] font-bold text-slate-500 mb-1.5">テーマカラーを選択</label>
                    <div id="modalColorPalette" class="grid grid-cols-6 gap-2 max-h-36 overflow-y-auto p-1 bg-slate-50 border rounded-lg">
                        <!-- JavaScriptで動的に全12色を描画 -->
                    </div>
                </div>
                <!-- エラーメッセージ用 -->
                <p id="modalErrorMessage" class="text-[10px] text-rose-500 font-bold hidden"></p>
            </div>

            <div class="flex justify-end gap-2 pt-2">
                <button onclick="closeAddSubjectModal()" class="px-4 py-2 bg-slate-100 hover:bg-slate-200 rounded-xl text-xs font-bold text-slate-600 transition-colors">キャンセル</button>
                <button onclick="submitAddSubjectFromModal()" class="px-4 py-2 bg-indigo-600 hover:bg-indigo-700 rounded-xl text-xs font-bold text-white transition-colors">登録する</button>
            </div>
        </div>
    </div>

    <!-- グローバルカラーピッカー (ダッシュボード等での簡易色変更用) -->
    <div id="globalColorPicker" class="fixed hidden bg-white border border-slate-200 rounded-xl shadow-xl p-2 gap-1 z-[120] flex flex-wrap max-w-[200px]"></div>

    <!-- 確認ダイアログモーダル -->
    <div id="customConfirmModal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm flex items-center justify-center hidden z-[100] p-4">
        <div class="bg-white rounded-2xl p-6 max-w-sm w-full shadow-2xl border border-slate-100 space-y-4 transform scale-95 transition-all">
            <div class="flex items-center gap-3 text-indigo-600" id="confirmModalHeader">
                <div class="p-2 bg-indigo-50 rounded-lg" id="confirmModalIconBox">
                    <i data-lucide="help-circle" class="w-6 h-6" id="confirmModalIcon"></i>
                </div>
                <h4 class="text-base font-black" id="confirmModalTitle">確認</h4>
            </div>
            <p id="confirmModalMessage" class="text-xs text-slate-600 leading-relaxed font-medium"></p>
            <div class="flex justify-end gap-2 pt-2">
                <button id="confirmCancelBtn" class="px-4 py-2 bg-slate-100 hover:bg-slate-200 rounded-xl text-xs font-bold text-slate-600 transition-colors">キャンセル</button>
                <button id="confirmOkBtn" class="px-4 py-2 bg-indigo-600 hover:bg-indigo-700 rounded-xl text-xs font-bold text-white transition-colors">確認</button>
            </div>
        </div>
    </div>

    <!-- トースト通知 -->
    <div id="toast" class="fixed bottom-6 right-6 bg-slate-800 text-white px-5 py-3 rounded-xl shadow-lg flex items-center gap-3 border border-slate-700 transform translate-y-20 opacity-0 transition-all duration-300 pointer-events-none z-50 font-bold font-sans">
        <i data-lucide="check-circle" class="w-5 h-5 text-emerald-400"></i>
        <span id="toastMessage" class="text-xs font-bold">自動保存されました。</span>
    </div>

    <!-- フッター -->
    <footer class="bg-slate-100 border-t border-slate-200 text-center py-4 text-xs text-slate-400 mt-auto">
        <div class="max-w-full mx-auto px-4 sm:px-8 flex flex-col sm:flex-row justify-between items-center gap-2">
            <p>&copy; 2026 学習プランナー. All Rights Reserved.</p>
            <div class="flex gap-4">
                <button onclick="resetAllDataWithConfirm()" class="text-rose-500 hover:text-rose-600 transition-colors font-medium">データを初期化</button>
            </div>
        </div>
    </footer>

    <script>
        // --- iframe 内でも安全に localStorage を使うためのラッパー ---
        const safeStorage = {
            getItem(key) {
                try {
                    return localStorage.getItem(key);
                } catch (e) {
                    console.warn("Storage access denied: fallback to in-memory store.", e);
                    return null;
                }
            },
            setItem(key, value) {
                try {
                    localStorage.setItem(key, value);
                } catch (e) {
                    console.warn("Storage access denied: cannot save permanently.", e);
                }
            },
            clear() {
                try {
                    localStorage.clear();
                } catch (e) {
                    console.warn("Storage access denied: cannot clear permanently.", e);
                }
            }
        };

        // --- トースト通知機能 ---
        function showToast(msg) {
            const toast = document.getElementById('toast');
            const msgEl = document.getElementById('toastMessage');
            if (toast && msgEl) {
                msgEl.innerText = msg;
                toast.classList.remove('translate-y-20', 'opacity-0');
                toast.classList.add('translate-y-0', 'opacity-100');
                setTimeout(() => {
                    toast.classList.remove('translate-y-0', 'opacity-100');
                    toast.classList.add('translate-y-20', 'opacity-0');
                }, 3000);
            }
        }

        // --- アプリケーションのグローバルステート ---
        const todayDateObj = new Date();
        let currentYear = todayDateObj.getFullYear();
        let currentMonth = todayDateObj.getMonth() + 1; 
        let currentSelectedDay = todayDateObj.getDate(); 
        
        let trendViewMode = 'week'; 
        let subjects = ["国語", "数学", "英語", "社会", "理科"];
        let selectedBrush = null; // 現在選択中のブラシ

        // 週を特定するためのキー
        let currentWeekKey = "";

        let appData = {
            monthlyProgress: {},
            dailyTimelines: {}, 
            subjectColors: {},
            timerSlotsFocus: [], 
            timerSlotsBreak: [], 
            pomodoroAutoLoop: false,
            // 週間計画シート用追加データ
            weeklyGoals: {},
            weeklyReviews: {},
            weeklyToDos: {},
            dailyToDos: {},
            dailyGoals: {}
        };

        let timerSecondsTotal = 25 * 60; 
        let timerSecondsLeft = 25 * 60;
        let timerStateMode = 'focus'; 
        let timerSubjectSelected = "国語";
        let timerIntervalId = null;
        let timerIsRunning = false;

        let timerIsOvertime = false;
        let timerOvertimeSeconds = 0;
        let alarmIntervalId = null;
        let audioCtx = null;
        let editingTimerSlotIndex = null; 

        let modalSelectedColor = 'indigo';

        const colorPalette = {
            indigo: { bg: 'bg-indigo-500', text: 'text-indigo-600', dot: '#6366f1', light: 'bg-indigo-50', border: 'border-indigo-200' },
            emerald: { bg: 'bg-emerald-500', text: 'text-emerald-600', dot: '#10b981', light: 'bg-emerald-50', border: 'border-emerald-200' },
            amber: { bg: 'bg-amber-500', text: 'text-amber-600', dot: '#f59e0b', light: 'bg-amber-50', border: 'border-amber-200' },
            rose: { bg: 'bg-rose-500', text: 'text-rose-600', dot: '#f43f5e', light: 'bg-rose-50', border: 'border-rose-200' },
            violet: { bg: 'bg-violet-500', text: 'text-violet-600', dot: '#8b5cf6', light: 'bg-violet-50', border: 'border-violet-200' },
            sky: { bg: 'bg-sky-500', text: 'text-sky-600', dot: '#0ea5e9', light: 'bg-sky-50', border: 'border-sky-200' },
            orange: { bg: 'bg-orange-500', text: 'text-orange-600', dot: '#f97316', light: 'bg-orange-50', border: 'border-orange-200' },
            teal: { bg: 'bg-teal-500', text: 'text-teal-600', dot: '#14b8a6', light: 'bg-teal-50', border: 'border-teal-200' },
            fuchsia: { bg: 'bg-fuchsia-500', text: 'text-fuchsia-600', dot: '#d946ef', light: 'bg-fuchsia-50', border: 'border-fuchsia-200' },
            lime: { bg: 'bg-lime-500', text: 'text-lime-600', dot: '#84cc16', light: 'bg-lime-50', border: 'border-lime-200' },
            cyan: { bg: 'bg-cyan-500', text: 'text-cyan-600', dot: '#06b6d4', light: 'bg-cyan-50', border: 'border-cyan-200' },
            pink: { bg: 'bg-pink-500', text: 'text-pink-600', dot: '#ec4899', light: 'bg-pink-50', border: 'border-pink-200' }
        };

        const tipsList = [
            "バーチカル表で「予定」と「記録」のマスをタップして、ルーズリーフ手帳感覚で直感的にスケジュールを記録できます！",
            "マスの消去は「消しゴム」ツールを選んでから対象のマスをタップしてください。",
            "タイマーが終了すると超過時間を自動計測！「完了して記録」を押すまでアラームと計測が続きます。",
            "集中と休憩の自動ループをONにすると、次のポモドーロセッションがハンズフリーで自動スタートします！"
        ];

        let pieChartInstance = null;
        let trendChartInstance = null;

        window.addEventListener('DOMContentLoaded', () => {
            loadFromLocalStorage();
            initApp();
            
            // 外側クリックでポップアップやパネルを閉じる処理
            document.addEventListener('click', (e) => {
                if (!e.target) return;
                const picker = document.getElementById('globalColorPicker');
                if (picker && !picker.contains(e.target) && (!e.target.classList || !e.target.classList.contains('subject-color-dot'))) {
                    picker.classList.add('hidden');
                }
                const monthPanel = document.getElementById('globalMonthPickerPanel');
                const monthBtn = document.getElementById('currentMonthLabelBtn');
                if (monthPanel && !monthPanel.contains(e.target) && monthBtn && !monthBtn.contains(e.target)) {
                    monthPanel.classList.add('hidden');
                }
                const calPanel = document.getElementById('dailyCalendarDropdown');
                const calBtn = document.getElementById('dailyCalendarBtn');
                if (calPanel && !calPanel.contains(e.target) && calBtn && !calBtn.contains(e.target)) {
                    calPanel.classList.add('hidden');
                }
            });
        });

        function safeCreateIcons() {
            if (typeof lucide !== 'undefined' && lucide.createIcons) {
                try {
                    lucide.createIcons();
                } catch (err) {
                    console.error("Lucide icons failed:", err);
                }
            }
        }

        // --- カスタム確認モーダル制御 ---
        function openCustomConfirm({ title, message, onConfirm, icon = 'help-circle', colorClass = 'indigo', okText = '確認', cancelText = 'キャンセル' }) {
            const modal = document.getElementById('customConfirmModal');
            const titleEl = document.getElementById('confirmModalTitle');
            const msgEl = document.getElementById('confirmModalMessage');
            const okBtn = document.getElementById('confirmOkBtn');
            const cancelBtn = document.getElementById('confirmCancelBtn');
            const iconBox = document.getElementById('confirmModalIconBox');
            const header = document.getElementById('confirmModalHeader');

            if (!modal || !titleEl || !msgEl || !okBtn || !cancelBtn) return;

            titleEl.innerText = title;
            msgEl.innerText = message;
            okBtn.innerText = okText;
            cancelBtn.innerText = cancelText;

            header.className = `flex items-center gap-3 text-${colorClass}-600`;
            iconBox.className = `p-2 bg-${colorClass}-50 rounded-lg`;
            
            const iconEl = document.getElementById('confirmModalIcon');
            if (iconEl) {
                iconEl.setAttribute('data-lucide', icon);
            }
            safeCreateIcons();

            okBtn.className = `px-4 py-2 bg-${colorClass}-600 hover:bg-${colorClass}-700 rounded-xl text-xs font-bold text-white transition-colors`;

            modal.classList.remove('hidden');

            okBtn.onclick = () => {
                modal.classList.add('hidden');
                if (onConfirm) onConfirm();
            };

            cancelBtn.onclick = () => {
                modal.classList.add('hidden');
            };
        }

        // --- 週の範囲計算ロジック（月曜日始まり） ---
        function getWeekRange(date) {
            const d = new Date(date);
            const day = d.getDay();
            const diff = d.getDate() - day + (day === 0 ? -6 : 1); // 月曜日を取得
            const monday = new Date(d.setDate(diff));
            
            const weekDays = [];
            for (let i = 0; i < 7; i++) {
                const nextDay = new Date(monday);
                nextDay.setDate(monday.getDate() + i);
                weekDays.push(nextDay);
            }
            return weekDays;
        }

        function getWeekKey(mondayDate) {
            return `${mondayDate.getFullYear()}-${mondayDate.getMonth() + 1}-${mondayDate.getDate()}`;
        }

        // --- ルーズリーフ中央のバインダーリング装飾を動的生成 ---
        function renderBinderRings() {
            const container = document.getElementById('binderRingsContainer');
            if (!container) return;
            container.innerHTML = '';
            for (let i = 0; i < 18; i++) {
                const ring = document.createElement('div');
                ring.className = "flex items-center justify-center h-5 w-full my-0.5";
                ring.innerHTML = `
                    <div class="w-2 h-2 bg-slate-200 rounded-full border border-slate-300 shadow-inner"></div>
                    <div class="w-6 h-2.5 bg-gradient-to-r from-slate-400 via-slate-100 to-slate-400 rounded-full -ml-3.5 z-10 shadow-md"></div>
                    <div class="w-2 h-2 bg-slate-200 rounded-full border border-slate-300 shadow-inner -ml-3.5"></div>
                `;
                container.appendChild(ring);
            }
        }

        // --- 教科追加ポップアップモーダルの制御 ---
        function openAddSubjectModal() {
            const modal = document.getElementById('addSubjectModal');
            const input = document.getElementById('modalSubjectNameInput');
            const errorMsg = document.getElementById('modalErrorMessage');
            
            input.value = '';
            errorMsg.classList.add('hidden');
            modalSelectedColor = 'indigo'; 
            
            renderModalColorPalette();
            modal.classList.remove('hidden');
            input.focus();
        }

        function closeAddSubjectModal() {
            const modal = document.getElementById('addSubjectModal');
            modal.classList.add('hidden');
        }

        function renderModalColorPalette() {
            const container = document.getElementById('modalColorPalette');
            if (!container) return;
            container.innerHTML = '';

            Object.keys(colorPalette).forEach(colorKey => {
                const colorConfig = colorPalette[colorKey];
                const btn = document.createElement('button');
                btn.type = 'button';
                btn.className = `w-10 h-10 rounded-xl ${colorConfig.bg} transition-all relative flex items-center justify-center hover:scale-105 active:scale-95 shadow-sm`;
                
                if (modalSelectedColor === colorKey) {
                    btn.classList.add('ring-4', 'ring-indigo-600', 'ring-offset-2');
                    btn.innerHTML = `<i data-lucide="check" class="w-5 h-5 text-white"></i>`;
                }
                
                btn.onclick = () => {
                    modalSelectedColor = colorKey;
                    renderModalColorPalette();
                };
                container.appendChild(btn);
            });
            safeCreateIcons();
        }

        function submitAddSubjectFromModal() {
            const input = document.getElementById('modalSubjectNameInput');
            const errorMsg = document.getElementById('modalErrorMessage');
            const val = input.value.trim();

            if (!val) {
                errorMsg.innerText = "教科名を入力してください。";
                errorMsg.classList.remove('hidden');
                return;
            }
            if (subjects.includes(val)) {
                errorMsg.innerText = "すでにその名前の教科が登録されています。";
                errorMsg.classList.remove('hidden');
                return;
            }

            subjects.push(val);
            appData.subjectColors[val] = modalSelectedColor;
            selectedBrush = val; 

            closeAddSubjectModal();
            initApp();
            saveAllData(); 
            showToast(`🎨 教科「${val}」を登録しました！`);
        }

        // --- 自動ループのON/OFF（ポモドーロモード用） ---
        function toggleAutoLoopSetting(checked) {
            appData.pomodoroAutoLoop = checked;
            saveAllData();
            showToast(checked ? "🔄 自動ループを有効にしました" : "⏸️ 自動ループを無効にしました");
        }

        // --- ポモドーロテクニック 一発簡単セット機能 ---
        function setPomodoroTechnique() {
            timerStateMode = 'focus';
            appData.pomodoroAutoLoop = true;
            
            const autoLoopToggle = document.getElementById('pomodoroAutoLoopToggle');
            if (autoLoopToggle) {
                autoLoopToggle.checked = true;
            }

            const focusBtn = document.getElementById('timerModeFocusBtn');
            const breakBtn = document.getElementById('timerModeBreakBtn');
            if (focusBtn) focusBtn.className = "flex-grow py-2 text-xs font-black rounded-lg bg-indigo-600 text-white shadow-sm transition-all";
            if (breakBtn) breakBtn.className = "flex-grow py-2 text-xs font-bold rounded-lg text-slate-600 hover:text-slate-800 transition-all";
            
            document.getElementById('bigTimerTitle').innerText = "READY TO STUDY (POMODORO)";
            document.getElementById('bigTimerTitle').className = "block text-[10px] font-black text-indigo-400 uppercase tracking-wider";

            timerIsOvertime = false;
            timerOvertimeSeconds = 0;
            timerSecondsTotal = 25 * 60;
            timerSecondsLeft = timerSecondsTotal;

            saveAllData();
            initApp();
            showToast("⏱️ ポモドーロテクニック（25分集中＋5分休憩自動サイクル）をセットしました！");
        }

        function initApp() {
            if (!selectedBrush || (selectedBrush !== 'eraser' && !subjects.includes(selectedBrush))) {
                selectedBrush = subjects.length > 0 ? subjects[0] : 'eraser';
            }
            updateGlobalMonthUI();
            renderMonthPickerGrid();
            renderDashboardSubjects();
            renderMonthlyTable();
            renderDailyView();
            renderWeeklyView(); // 週間手帳ビューのレンダラー起動
            renderTimerPresets();
            renderTimerClassifications();
            updateTimerDisplay();
            initCharts();
            generateNewTip();
            safeCreateIcons();
        }

        // --- データ保持、ローカルストレージ設定 ---
        function loadFromLocalStorage() {
            const savedSubjects = safeStorage.getItem('study_planner_subjects');
            if (savedSubjects) {
                try {
                    const parsed = JSON.parse(savedSubjects);
                    if (Array.isArray(parsed)) subjects = parsed;
                } catch(e) {
                    console.warn("Error parsing subjects from storage:", e);
                }
            }

            const savedData = safeStorage.getItem('study_planner_appdata');
            if (savedData) {
                try {
                    appData = JSON.parse(savedData);
                } catch(e) {
                    console.warn("Error parsing appData from storage:", e);
                }
            }
            
            if (!appData) {
                appData = {};
            }
            if (!appData.monthlyProgress) appData.monthlyProgress = {};
            if (!appData.dailyTimelines) appData.dailyTimelines = {};
            if (!appData.subjectColors) appData.subjectColors = {};
            
            // 週間手帳用データ格納庫の健全性チェック
            if (!appData.weeklyGoals) appData.weeklyGoals = {};
            if (!appData.weeklyReviews) appData.weeklyReviews = {};
            if (!appData.weeklyToDos) appData.weeklyToDos = {};
            if (!appData.dailyToDos) appData.dailyToDos = {};
            if (!appData.dailyGoals) appData.dailyGoals = {};

            // 集中マイタイマーのデフォルト5枠
            if (!appData.timerSlotsFocus || appData.timerSlotsFocus.length !== 5) {
                appData.timerSlotsFocus = [
                    { label: '勉強集中ポモドーロ', mins: 25 },
                    { label: 'サクッと英単語', mins: 10 },
                    { label: 'じっくり数学問題', mins: 50 },
                    { label: '読書・インプット', mins: 20 },
                    { label: '定期テスト対策', mins: 45 }
                ];
            }

            // 休憩マイタイマーのデフォルト5枠
            if (!appData.timerSlotsBreak || appData.timerSlotsBreak.length !== 5) {
                appData.timerSlotsBreak = [
                    { label: 'リフレッシュ休憩', mins: 5 },
                    { label: 'ちょっと長め休憩', mins: 15 },
                    { label: 'お茶・水分補給', mins: 8 },
                    { label: 'ストレッチ体操', mins: 10 },
                    { label: 'リラックス音楽', mins: 12 }
                ];
            }

            if (appData.pomodoroAutoLoop === undefined) {
                appData.pomodoroAutoLoop = false;
            }
            const autoLoopToggle = document.getElementById('pomodoroAutoLoopToggle');
            if (autoLoopToggle) {
                autoLoopToggle.checked = appData.pomodoroAutoLoop;
            }

            migrateDataToConsolidated();

            subjects.forEach((sub, i) => {
                if (!appData.subjectColors[sub]) {
                    const keys = Object.keys(colorPalette);
                    appData.subjectColors[sub] = keys[i % keys.length];
                }
            });
        }

        function migrateDataToConsolidated() {
            if (!appData.dailyTimelines) {
                appData.dailyTimelines = {};
                return;
            }
            for (let dayKey in appData.dailyTimelines) {
                const dayData = appData.dailyTimelines[dayKey];
                if (dayData && !dayData.plans && !dayData.actuals) {
                    const plans = Array(48).fill(null);
                    const actuals = Array(48).fill(null);
                    
                    for (let key in dayData) {
                        if (Array.isArray(dayData[key])) {
                            dayData[key].forEach((val, idx) => {
                                if (val === 1 || val === 3) plans[idx] = key;
                                if (val === 2 || val === 3) actuals[idx] = key;
                            });
                        }
                    }
                    appData.dailyTimelines[dayKey] = { plans, actuals };
                }
            }
        }

        function getOrInitDayTimeline(dayKey) {
            if (!appData.dailyTimelines[dayKey]) {
                appData.dailyTimelines[dayKey] = {
                    plans: Array(48).fill(null),
                    actuals: Array(48).fill(null)
                };
            }
            if (!appData.dailyTimelines[dayKey].plans) {
                appData.dailyTimelines[dayKey].plans = Array(48).fill(null);
            }
            if (!appData.dailyTimelines[dayKey].actuals) {
                appData.dailyTimelines[dayKey].actuals = Array(48).fill(null);
            }
            return appData.dailyTimelines[dayKey];
        }

        // --- 自動保存（バックグラウンド自動実行） ---
        function saveAllData(silent = false) {
            safeStorage.setItem('study_planner_subjects', JSON.stringify(subjects));
            safeStorage.setItem('study_planner_appdata', JSON.stringify(appData));
            if (!silent) {
                showToast("💾 リアルタイム自動保存しました。");
            }
            updateDashboardStats();
            updateCharts();
        }

        function resetAllDataWithConfirm() {
            openCustomConfirm({
                title: 'データの初期化',
                message: 'すべての学習データを初期化してもよろしいですか？この操作は取り消せません。',
                icon: 'trash-2',
                colorClass: 'rose',
                okText: '初期化する',
                onConfirm: () => {
                    safeStorage.clear();
                    subjects = ["国語", "数学", "英語", "社会", "理科"];
                    appData = { monthlyProgress: {}, dailyTimelines: {}, subjectColors: {} };
                    selectedBrush = "国語";
                    initApp();
                    showToast("🔄 データを初期化しました。");
                }
            });
        }

        // --- タブ切り替え ---
        function switchTab(tabId) {
            document.querySelectorAll('.tab-content').forEach(el => el.classList.add('hidden'));
            document.getElementById(`content-${tabId}`).classList.remove('hidden');

            document.querySelectorAll('.tab-btn').forEach(btn => {
                btn.classList.remove('border-indigo-600', 'text-indigo-600');
                btn.classList.add('border-transparent', 'text-slate-500');
            });
            const activeBtn = document.getElementById(`tab-${tabId}`);
            if (activeBtn) {
                activeBtn.classList.remove('border-transparent', 'text-slate-500');
                activeBtn.classList.add('border-indigo-600', 'text-indigo-600');
            }

            if (tabId === 'dashboard') {
                updateDashboardStats();
                updateCharts();
            } else if (tabId === 'weekly') {
                renderWeeklyView();
            }
            safeCreateIcons();
        }

        // --- 月選択 ---
        function updateGlobalMonthUI() {
            document.getElementById('currentMonthLabel').innerText = `${currentYear}年${currentMonth}月`;
            document.getElementById('monthlyTitle').innerText = `${currentMonth}月の学習進捗表`;
            document.getElementById('pickerYearSelect').value = currentYear;
        }

        function changeMonth(dir) {
            currentMonth += dir;
            if (currentMonth > 12) { currentMonth = 1; currentYear++; }
            if (currentMonth < 1) { currentMonth = 12; currentYear--; }
            updateGlobalMonthUI();
            initApp();
        }

        function toggleGlobalMonthPicker(e) {
            e.stopPropagation();
            const panel = document.getElementById('globalMonthPickerPanel');
            panel.classList.toggle('hidden');
        }

        function renderMonthPickerGrid() {
            const grid = document.getElementById('monthPickerGrid');
            grid.innerHTML = '';
            const temp = document.getElementById('month-picker-btn-template');
            for (let m = 1; m <= 12; m++) {
                const clone = temp.content.cloneNode(true);
                const btn = clone.querySelector('button');
                btn.innerText = `${m}月`;
                if (m === currentMonth) {
                    btn.classList.add('bg-indigo-600', 'text-white', 'hover:bg-indigo-700');
                }
                btn.onclick = () => {
                    currentYear = parseInt(document.getElementById('pickerYearSelect').value);
                    currentMonth = m;
                    document.getElementById('globalMonthPickerPanel').classList.add('hidden');
                    updateGlobalMonthUI();
                    initApp();
                };
                grid.appendChild(clone);
            }
        }

        // --- 年月＆日付ナビゲーション ---
        function navigateCalendarMonth(dir, e) {
            e.stopPropagation();
            currentMonth += dir;
            if (currentMonth > 12) { currentMonth = 1; currentYear++; }
            if (currentMonth < 1) { currentMonth = 12; currentYear--; }
            currentSelectedDay = 1;
            updateGlobalMonthUI();
            renderDailyCalendarDropdownGrid();
            renderDailyView();
            renderWeeklyView();
        }

        function jumpToTodayInCalendar(e) {
            e.stopPropagation();
            const now = new Date();
            currentYear = now.getFullYear();
            currentMonth = now.getMonth() + 1;
            currentSelectedDay = now.getDate();
            updateGlobalMonthUI();
            document.getElementById('dailyCalendarDropdown').classList.add('hidden');
            renderDailyView();
            renderWeeklyView();
        }

        function getDaysInMonth(year, month) {
            return new Date(year, month, 0).getDate();
        }

        // --- 教科削除 ---
        function openDeleteModal(subName) {
            openCustomConfirm({
                title: '教科の削除確認',
                message: `「${subName}」を削除してもよろしいですか？関連するタイムラインや実績などのデータがすべて初期化されます。`,
                icon: 'trash-2',
                colorClass: 'rose',
                okText: '削除する',
                onConfirm: () => {
                    subjects = subjects.filter(s => s !== subName);
                    delete appData.subjectColors[subName];
                    
                    for (let dayKey in appData.dailyTimelines) {
                        const dayData = appData.dailyTimelines[dayKey];
                        if (dayData) {
                            if (dayData.plans) {
                                dayData.plans = dayData.plans.map(val => val === subName ? null : val);
                            }
                            if (dayData.actuals) {
                                dayData.actuals = dayData.actuals.map(val => val === subName ? null : val);
                            }
                        }
                    }

                    if (selectedBrush === subName) {
                        selectedBrush = subjects.length > 0 ? subjects[0] : 'eraser';
                    }

                    initApp();
                    saveAllData(); 
                }
            });
        }

        function showColorPicker(e, subName) {
            e.stopPropagation();
            const picker = document.getElementById('globalColorPicker');
            picker.innerHTML = '';
            Object.keys(colorPalette).forEach(cName => {
                const dot = document.createElement('button');
                dot.className = `w-6 h-6 rounded-full ${colorPalette[cName].bg} border-2 ${appData.subjectColors[subName] === cName ? 'border-slate-900' : 'border-white'} hover:scale-110 transition-transform`;
                dot.onclick = () => {
                    appData.subjectColors[subName] = cName;
                    picker.classList.add('hidden');
                    initApp();
                    saveAllData(true); 
                };
                picker.appendChild(dot);
            });
            picker.classList.remove('hidden');
            const rect = e.target.getBoundingClientRect();
            picker.style.top = `${rect.bottom + window.scrollY + 5}px`;
            picker.style.left = `${rect.left + window.scrollX}px`;
        }

        // --- ダッシュボード ---
        function generateNewTip() {
            const idx = Math.floor(Math.random() * tipsList.length);
            document.getElementById('dashboardTips').innerText = tipsList[idx];
        }

        function renderDashboardSubjects() {
            const container = document.getElementById('dashboardSubjectsList');
            container.innerHTML = '';
            if (subjects.length === 0) {
                container.innerHTML = `<p class="text-xs text-slate-400">登録されている教科がありません。上の「教科を追加」ボタンから追加してください。</p>`;
                return;
            }
            subjects.forEach(sub => {
                const c = colorPalette[appData.subjectColors[sub] || 'indigo'];
                const div = document.createElement('div');
                div.className = "flex items-center justify-between p-2.5 bg-slate-50 border border-slate-100 rounded-xl";
                div.innerHTML = `
                    <div class="flex items-center gap-2">
                        <button onclick="showColorPicker(event, '${sub}')" class="w-4 h-4 rounded-full ${c.bg} subject-color-dot animate-pulse" title="色を変更"></button>
                        <span class="font-bold text-xs text-slate-700">${sub}</span>
                    </div>
                    <button onclick="openDeleteModal('${sub}')" class="p-1 hover:bg-slate-200 text-slate-400 hover:text-rose-600 rounded transition">
                        <i data-lucide="trash-2" class="w-3.5 h-3.5"></i>
                    </button>
                `;
                container.appendChild(div);
            });
            safeCreateIcons();
        }

        function updateDashboardStats() {
            const daysCount = getDaysInMonth(currentYear, currentMonth);
            let totalMins = 0;
            let activeDaysSet = new Set();

            for (let d = 1; d <= daysCount; d++) {
                const dayKey = `${currentYear}-${currentMonth}-${d}`;
                const dayData = appData.dailyTimelines[dayKey];
                if (dayData && dayData.actuals) {
                    dayData.actuals.forEach(val => {
                        if (val !== null) totalMins += 30;
                    });
                }
                const progressKey = `${currentYear}-${currentMonth}-${d}`;
                if (appData.monthlyProgress[progressKey]) {
                    let hasContent = Object.values(appData.monthlyProgress[progressKey]).some(v => v && v.trim() !== '');
                    if (hasContent) activeDaysSet.add(d);
                }
            }

            document.getElementById('stat-total-time').innerText = `${(totalMins / 60).toFixed(1)}時間`;
            document.getElementById('stat-active-days').innerText = `${activeDaysSet.size}日`;
            document.getElementById('stat-subjects-count').innerText = `${subjects.length}教科`;

            // 今日の達成率計算
            const todayKey = `${currentYear}-${currentMonth}-${currentSelectedDay}`;
            const todayData = getOrInitDayTimeline(todayKey);
            let plannedMins = 0;
            let actualMins = 0;
            
            todayData.plans.forEach(val => { if (val !== null) plannedMins += 30; });
            todayData.actuals.forEach(val => { if (val !== null) actualMins += 30; });

            let rate = plannedMins > 0 ? Math.round((actualMins / plannedMins) * 100) : 0;
            if (rate > 100) rate = 100;
            document.getElementById('stat-today-completion').innerText = `${rate}%`;
        }

        // --- 月間進捗表 ---
        function renderMonthlyTable() {
            const container = document.getElementById('customHeadersContainer');
            if (!container) return;
            container.innerHTML = '';
            subjects.forEach(sub => {
                const th = document.createElement('th');
                th.className = "py-3.5 px-2 text-xs font-black text-slate-600 min-w-[120px] border-r border-slate-200 relative group";
                th.innerHTML = `
                    <span>${sub}</span>
                    <button onclick="openDeleteModal('${sub}')" class="absolute right-1 top-1/2 -translate-y-1/2 opacity-0 group-hover:opacity-100 p-0.5 hover:bg-slate-200 text-slate-400 hover:text-rose-600 rounded transition" title="教科を削除">
                        <i data-lucide="x" class="w-3 h-3"></i>
                    </button>
                `;
                container.appendChild(th);
            });

            const tbody = document.getElementById('monthlyTableBody');
            if (!tbody) return;
            tbody.innerHTML = '';
            const totalDays = getDaysInMonth(currentYear, currentMonth);

            for (let d = 1; d <= totalDays; d++) {
                const tr = document.createElement('tr');
                tr.className = "hover:bg-slate-50/50 transition-colors";
                
                let dayLabelClass = "font-bold text-xs";
                const dateObj = new Date(currentYear, currentMonth - 1, d);
                const wDay = dateObj.getDay();
                if (wDay === 0) dayLabelClass += " text-rose-500 bg-rose-50/30";
                if (wDay === 6) dayLabelClass += " text-sky-500 bg-sky-50/30";

                const dayKey = `${currentYear}-${currentMonth}-${d}`;
                if (!appData.monthlyProgress[dayKey]) appData.monthlyProgress[dayKey] = {};

                let subCellsHtml = '';
                subjects.forEach(sub => {
                    const currentVal = appData.monthlyProgress[dayKey][sub] || '';
                    subCellsHtml += `
                        <td class="p-1 border-r border-slate-200">
                            <input type="text" value="${escapeHtml(currentVal)}" 
                                onchange="updateMonthlyCell(${d}, '${escapeJsString(sub)}', this.value)"
                                placeholder="..." 
                                class="w-full bg-transparent px-2 py-1 text-xs text-center focus:bg-white focus:outline-none focus:ring-1 focus:ring-indigo-500 rounded font-medium">
                        </td>
                    `;
                });

                const memoVal = appData.monthlyProgress[dayKey]['__memo'] || '';

                tr.innerHTML = `
                    <td class="py-2 px-1 border-r border-slate-200 ${dayLabelClass} select-none">
                        <button onclick="jumpToDailyDay(${d})" class="hover:underline text-left block w-full" title="この日のデイリーシートへ移動">
                            ${d}日(${['日','月','火','水','木','金','土'][wDay]})
                        </button>
                    </td>
                    ${subCellsHtml}
                    <td class="p-1 bg-slate-50/40">
                        <input type="text" value="${escapeHtml(memoVal)}" 
                            onchange="updateMonthlyCell(${d}, '__memo', this.value)"
                            placeholder="メモ欄..." 
                            class="w-full bg-transparent px-2 py-1 text-xs text-left focus:bg-white focus:outline-none focus:ring-1 focus:ring-emerald-500 rounded text-slate-500">
                    </td>
                `;
                tbody.appendChild(tr);
            }
            safeCreateIcons();
        }

        function updateMonthlyCell(day, key, value) {
            const dayKey = `${currentYear}-${currentMonth}-${day}`;
            if (!appData.monthlyProgress[dayKey]) appData.monthlyProgress[dayKey] = {};
            appData.monthlyProgress[dayKey][key] = value;
            if (day === currentSelectedDay) {
                renderDailySubjectsList();
            }
            saveAllData(true); 
        }

        // --- 日次計画シート ---
        function jumpToDailyDay(d) {
            currentSelectedDay = d;
            switchTab('daily');
        }

        function navigateDailyDay(dir) {
            const totalDays = getDaysInMonth(currentYear, currentMonth);
            currentSelectedDay += dir;
            if (currentSelectedDay > totalDays) {
                currentSelectedDay = 1;
                changeMonth(1);
                return;
            }
            if (currentSelectedDay < 1) {
                changeMonth(-1);
                const prevTotal = getDaysInMonth(currentYear, currentMonth);
                currentSelectedDay = prevTotal;
                return;
            }
            renderDailyView();
        }

        function toggleDailyCalendarPopup(e) {
            e.stopPropagation();
            document.getElementById('dailyCalendarDropdown').classList.toggle('hidden');
            renderDailyCalendarDropdownGrid();
        }

        function renderDailyCalendarDropdownGrid() {
            document.getElementById('calendarDropdownMonthLabel').innerText = `${currentYear}年${currentMonth}月`;
            const container = document.getElementById('calendarGridContainer');
            container.innerHTML = '';

            const firstDayIndex = new Date(currentYear, currentMonth - 1, 1).getDay();
            const totalDays = getDaysInMonth(currentYear, currentMonth);

            for (let i = 0; i < firstDayIndex; i++) {
                const empty = document.createElement('div');
                container.appendChild(empty);
            }

            const today = new Date();
            const isTodayInView = (today.getFullYear() === currentYear && (today.getMonth() + 1) === currentMonth);
            document.getElementById('calendarTodayIndicator').innerText = isTodayInView ? `今日: ${today.getDate()}日` : "今月以外表示中";

            for (let d = 1; d <= totalDays; d++) {
                const btn = document.createElement('button');
                btn.innerText = d;
                btn.className = "p-1.5 text-xs font-bold rounded-lg transition-all text-slate-700 hover:bg-indigo-50 ";
                if (d === currentSelectedDay) {
                    btn.className += " bg-indigo-600 text-white hover:bg-indigo-700 shadow-sm";
                } else if (isTodayInView && d === today.getDate()) {
                    btn.className += " border border-emerald-500 text-emerald-600";
                }
                btn.onclick = (e) => {
                    e.stopPropagation();
                    currentSelectedDay = d;
                    document.getElementById('dailyCalendarDropdown').classList.add('hidden');
                    renderDailyView();
                };
                container.appendChild(btn);
            }
        }

        function renderDailyView() {
            document.getElementById('selectedDayLabel').innerText = `${currentSelectedDay}日`;
            document.getElementById('dailyLogDateLabel').innerText = `${currentSelectedDay}日`;
            
            const dObj = new Date(currentYear, currentMonth - 1, currentSelectedDay);
            const wDayStr = ['日','月','火','水','木','金','土'][dObj.getDay()];
            document.getElementById('dailyLogWeekDayLabel').innerText = `(${wDayStr})`;

            const dayKey = `${currentYear}-${currentMonth}-${currentSelectedDay}`;
            getOrInitDayTimeline(dayKey);
            
            // 日誌読み込み
            const progressObj = appData.monthlyProgress[dayKey] || {};
            document.getElementById('dailyReflection').value = progressObj['__reflection'] || '';

            // 評価読み込み
            const currentEval = progressObj['__evaluation'] || 0;
            setEvaluationUI(currentEval);

            renderDailyTimelineGrid();
            renderDailySubjectsList();
            calculateDailySummary();
        }

        // --- パレットブラシ表示 ---
        function renderBrushPalette() {
            const container = document.getElementById('brushPaletteContainer');
            if (container) {
                container.innerHTML = '';
                fillBrushButtons(container, 'daily');
            }

            const weeklyContainer = document.getElementById('weeklyBrushPaletteContainer');
            if (weeklyContainer) {
                weeklyContainer.innerHTML = '';
                fillBrushButtons(weeklyContainer, 'weekly');
            }
        }

        function fillBrushButtons(targetContainer, viewType) {
            if (subjects.length === 0) {
                targetContainer.innerHTML = `<span class="text-xs text-slate-400">登録されている教科がありません。追加してください。</span>`;
                return;
            }

            subjects.forEach(sub => {
                const c = colorPalette[appData.subjectColors[sub] || 'indigo'];
                const isSelected = (selectedBrush === sub);
                const btn = document.createElement('button');
                btn.className = `px-3 py-1.5 rounded-full text-xs font-bold flex items-center gap-1.5 transition-all shadow-sm border ${
                    isSelected 
                    ? `ring-2 ring-slate-800 scale-105 border-slate-900 text-white ${c.bg}` 
                    : `bg-white hover:bg-slate-50 border-slate-200 text-slate-700`
                }`;
                btn.innerHTML = `
                    <span class="w-2.5 h-2.5 rounded-full ${isSelected ? 'bg-white' : c.bg}"></span>
                    <span>${sub}</span>
                `;
                btn.onclick = () => {
                    selectedBrush = sub;
                    renderBrushPalette();
                    if (viewType === 'weekly') {
                        renderWeeklyView();
                    } else {
                        renderDailyTimelineGrid();
                    }
                };
                targetContainer.appendChild(btn);
            });

            // 消しゴムツール
            const isEraserSelected = (selectedBrush === 'eraser');
            const eraserBtn = document.createElement('button');
            eraserBtn.className = `px-3 py-1.5 rounded-full text-xs font-bold flex items-center gap-1.5 transition-all shadow-sm border ${
                isEraserSelected 
                ? 'ring-2 ring-slate-600 scale-105 border-slate-900 bg-slate-700 text-white' 
                : 'bg-white hover:bg-slate-50 border-slate-200 text-slate-700'
            }`;
            eraserBtn.innerHTML = `
                <i data-lucide="eraser" class="w-3.5 h-3.5"></i>
                <span>消しゴム</span>
            `;
            eraserBtn.onclick = () => {
                selectedBrush = 'eraser';
                renderBrushPalette();
                if (viewType === 'weekly') {
                    renderWeeklyView();
                } else {
                    renderDailyTimelineGrid();
                }
            };
            targetContainer.appendChild(eraserBtn);
            safeCreateIcons();
        }

        // --- タイムライン描画 (バーチカル予定・実績列) ---
        function renderDailyTimelineGrid() {
            const timelinesBox = document.getElementById('dynamicTimelinesContainer');
            if (!timelinesBox) return;
            timelinesBox.innerHTML = '';

            const dayKey = `${currentYear}-${currentMonth}-${currentSelectedDay}`;
            const dayData = getOrInitDayTimeline(dayKey);

            // 0:00 から 23:30 までの48つの30分枠行を作成
            for (let i = 0; i < 48; i++) {
                const hour = Math.floor(i / 2);
                const min = i % 2 === 0 ? "00" : "30";
                const timeString = `${hour.toString().padStart(2, '0')}:${min}`;

                const row = document.createElement('div');
                row.className = "grid grid-cols-12 border-b border-slate-200 hover:bg-slate-50/80 items-center transition-colors";

                // 1. 時間ラベル列 (Col-span: 3)
                const timeCol = document.createElement('div');
                timeCol.className = "col-span-3 text-center py-2.5 font-mono text-xs font-black text-slate-500 border-r border-slate-200 bg-slate-50/60 select-none";
                timeCol.innerText = timeString;
                row.appendChild(timeCol);

                // 2. 予定 (Plan) セル列 (Col-span: 4)
                const planCol = document.createElement('div');
                planCol.className = "col-span-4 p-1 border-r border-slate-200 h-full flex items-center justify-center";
                
                const planSub = dayData.plans[i];
                const cellPlan = document.createElement('button');
                cellPlan.className = "w-full h-8 rounded-lg border transition-all text-[10px] font-bold flex items-center justify-center truncate focus:outline-none";
                
                if (planSub) {
                    const c = colorPalette[appData.subjectColors[planSub] || 'indigo'];
                    cellPlan.className += ` ${c.bg} ${c.border} text-white shadow-sm opacity-80`;
                    cellPlan.innerText = planSub;
                } else {
                    cellPlan.className += " bg-slate-50/50 border-dashed border-slate-200 text-slate-300 hover:bg-indigo-50/30";
                    cellPlan.innerText = "未設定";
                }

                cellPlan.onclick = () => {
                    if (selectedBrush === 'eraser') {
                        dayData.plans[i] = null;
                    } else if (selectedBrush) {
                        dayData.plans[i] = selectedBrush;
                    }
                    renderDailyTimelineGrid();
                    calculateDailySummary();
                    saveAllData(true); 
                };
                planCol.appendChild(cellPlan);
                row.appendChild(planCol);

                // 3. 実績 (Actual) セル列 (Col-span: 5)
                const actCol = document.createElement('div');
                actCol.className = "col-span-5 p-1 h-full flex items-center justify-center";

                const actSub = dayData.actuals[i];
                const cellAct = document.createElement('button');
                cellAct.className = "w-full h-8 rounded-lg border transition-all text-[10px] font-black flex items-center justify-center truncate focus:outline-none";

                if (actSub) {
                    const c = colorPalette[appData.subjectColors[actSub] || 'indigo'];
                    cellAct.className += ` ${c.bg} ${c.border} text-white shadow-md`;
                    cellAct.innerText = actSub;
                } else {
                    cellAct.className += " bg-slate-50 border-dashed border-slate-200 text-slate-400 hover:bg-emerald-50/30";
                    cellAct.innerText = "+ 記録を追加";
                }

                cellAct.onclick = () => {
                    if (selectedBrush === 'eraser') {
                        dayData.actuals[i] = null;
                    } else if (selectedBrush) {
                        dayData.actuals[i] = selectedBrush;
                    }
                    renderDailyTimelineGrid();
                    calculateDailySummary();
                    saveAllData(true); 
                };
                actCol.appendChild(cellAct);
                row.appendChild(actCol);

                timelinesBox.appendChild(row);
            }

            renderBrushPalette();
        }

        function renderDailySubjectsList() {
            const container = document.getElementById('dailySubjectsContainer');
            if (!container) return;
            container.innerHTML = '';
            const dayKey = `${currentYear}-${currentMonth}-${currentSelectedDay}`;
            if (!appData.monthlyProgress[dayKey]) appData.monthlyProgress[dayKey] = {};
            const progressObj = appData.monthlyProgress[dayKey];

            subjects.forEach(sub => {
                const c = colorPalette[appData.subjectColors[sub] || 'indigo'];
                
                // 実績時間(分)算出
                let actMins = 0;
                if (appData.dailyTimelines[dayKey] && appData.dailyTimelines[dayKey].actuals) {
                    appData.dailyTimelines[dayKey].actuals.forEach(val => {
                        if (val === sub) actMins += 30;
                    });
                }
                const hrsNum = (actMins / 60).toFixed(1);

                const div = document.createElement('div');
                div.className = "grid grid-cols-1 md:grid-cols-12 gap-3 items-center p-3 bg-slate-50 rounded-xl border border-slate-150";
                div.innerHTML = `
                    <div class="md:col-span-3 flex items-center gap-2">
                        <button onclick="showColorPicker(event, '${sub}')" class="w-3.5 h-3.5 rounded-full ${c.bg} flex-shrink-0 subject-color-dot animate-bounce" title="色を変更"></button>
                        <span class="font-black text-slate-700 text-xs truncate">${sub}</span>
                        <span class="ml-auto bg-emerald-50 text-emerald-700 border border-emerald-100 font-mono font-bold text-[10px] px-2 py-0.5 rounded-full">${hrsNum}h</span>
                    </div>
                    <div class="md:col-span-9">
                        <input type="text" value="${escapeHtml(progressObj[sub] || '')}"
                            onchange="updateDailySubjectText('${escapeJsString(sub)}', this.value)"
                            placeholder="${sub}で進めたテキスト名や実績内容を入力（進捗表と連動）..." 
                            class="w-full bg-white border border-slate-200 px-2.5 py-1.5 text-xs focus:ring-1 focus:ring-indigo-500 focus:outline-none rounded-lg text-slate-700 font-medium shadow-sm">
                    </div>
                `;
                container.appendChild(div);
            });

            const refl = document.getElementById('dailyReflection');
            if (refl) {
                refl.onchange = (e) => {
                    progressObj['__reflection'] = e.target.value;
                    saveAllData(true); 
                };
            }
        }

        function updateDailySubjectText(sub, val) {
            const dayKey = `${currentYear}-${currentMonth}-${currentSelectedDay}`;
            if (!appData.monthlyProgress[dayKey]) appData.monthlyProgress[dayKey] = {};
            appData.monthlyProgress[dayKey][sub] = val;
            saveAllData(true); 
        }

        function setEvaluation(val) {
            const dayKey = `${currentYear}-${currentMonth}-${currentSelectedDay}`;
            if (!appData.monthlyProgress[dayKey]) appData.monthlyProgress[dayKey] = {};
            appData.monthlyProgress[dayKey]['__evaluation'] = val;
            setEvaluationUI(val);
            saveAllData(true); 
        }

        function setEvaluationUI(val) {
            document.querySelectorAll('.eval-btn').forEach(b => b.classList.remove('ring-2', 'ring-indigo-500', 'bg-indigo-50/50', 'border-indigo-300'));
            if (val > 0) {
                const target = document.getElementById(`evalBtn${val}`);
                if (target) target.classList.add('ring-2', 'ring-indigo-500', 'bg-indigo-50/50', 'border-indigo-300');
            }
        }

        function calculateDailySummary() {
            const dayKey = `${currentYear}-${currentMonth}-${currentSelectedDay}`;
            const dayData = getOrInitDayTimeline(dayKey);

            let planMins = 0;
            let actMins = 0;

            dayData.plans.forEach(val => {
                if (val !== null) planMins += 30;
            });

            dayData.actuals.forEach(val => {
                if (val !== null) actMins += 30;
            });

            const actualTotalEl = document.getElementById('dailyActualTotal');
            const cumulativeTotalEl = document.getElementById('dailyCumulativeTotal');
            if (actualTotalEl) actualTotalEl.innerText = (actMins / 60).toFixed(1);
            if (cumulativeTotalEl) cumulativeTotalEl.innerText = actMins;

            const progressObj = appData.monthlyProgress[dayKey] || {};
            const savedPlanInput = document.getElementById('dailyPlannedTotal');
            if (savedPlanInput) {
                if (document.activeElement !== savedPlanInput) {
                    if (!progressObj['__planned_hours'] || progressObj['__planned_hours'] == '0') {
                        savedPlanInput.value = (planMins / 60).toFixed(1);
                        progressObj['__planned_hours'] = savedPlanInput.value;
                    } else {
                        savedPlanInput.value = progressObj['__planned_hours'] || '';
                    }
                } else {
                    progressObj['__planned_hours'] = savedPlanInput.value;
                }
            }
        }

        // ==========================================
        // --- 週間計画シート (Weekly View) ---
        // ==========================================
        function renderWeeklyView() {
            renderBinderRings(); // バインダー中央リングの描画

            // 今週の月曜〜日曜の日付を取得
            const weekDays = getWeekRange(new Date(currentYear, currentMonth - 1, currentSelectedDay));
            const monday = weekDays[0];
            const sunday = weekDays[6];

            currentWeekKey = getWeekKey(monday);

            // 週の範囲表示
            document.getElementById('weeklyWeekRangeLabel').innerText = `${monday.getFullYear()}/${monday.getMonth() + 1}/${monday.getDate()} 〜 ${sunday.getMonth() + 1}/${sunday.getDate()}`;
            document.getElementById('weeklyPageMonthLabel').innerText = `${monday.getMonth() + 1}`;

            // 今週の目標
            document.getElementById('weeklyGoalInput').value = appData.weeklyGoals[currentWeekKey] || '';
            // 今週の振り返り
            document.getElementById('weeklyReviewInput').value = appData.weeklyReviews[currentWeekKey] || '';

            // WEEKLY TO DO（今週の全体やること）の描画
            renderWeeklyToDoList();

            // 曜日カード（左ページ：月、火、水。右ページ：木、金、土、日）
            const leftContainer = document.getElementById('weeklyLeftDaysContainer');
            const rightContainer = document.getElementById('weeklyRightDaysContainer');
            
            if (leftContainer) leftContainer.innerHTML = '';
            if (rightContainer) rightContainer.innerHTML = '';

            let weekTotalMins = 0;

            weekDays.forEach((dayDate, idx) => {
                const dayY = dayDate.getFullYear();
                const dayM = dayDate.getMonth() + 1;
                const dayD = dayDate.getDate();
                const dayKey = `${dayY}-${dayM}-${dayD}`;
                
                const dayData = getOrInitDayTimeline(dayKey);
                const progressObj = appData.monthlyProgress[dayKey] || {};

                // 曜日ごとのTOTAL実績時間計算
                let dayMins = 0;
                dayData.actuals.forEach(val => {
                    if (val !== null) dayMins += 30;
                });
                weekTotalMins += dayMins;

                const hrs = Math.floor(dayMins / 60);
                const mins = dayMins % 60;
                const totalStr = `${hrs}h ${mins.toString().padStart(2, '0')}m`;

                // 曜日カラムのカードカード生成
                const card = document.createElement('div');
                card.className = "bg-white rounded-xl border border-slate-200/80 p-3 shadow-sm space-y-3 relative";
                
                const wDayJapanese = ['日', '月', '火', '水', '木', '金', '土'][dayDate.getDay()];
                
                // 曜日ごとのヘッダー色分け
                let headerBg = "bg-indigo-500";
                if (idx === 5) headerBg = "bg-sky-500"; // 土曜
                if (idx === 6) headerBg = "bg-rose-500"; // 日曜

                card.innerHTML = `
                    <!-- 曜日ヘッダー -->
                    <div class="flex items-center justify-between border-b pb-1.5">
                        <div class="flex items-center gap-1.5">
                            <span class="${headerBg} text-white font-black text-xs px-2 py-0.5 rounded-lg shrink-0">${dayM} / ${dayD} (${wDayJapanese})</span>
                        </div>
                        <button onclick="jumpToDailyDay(${dayD})" class="text-slate-400 hover:text-indigo-600 transition" title="この日のデイリーシートへ移動">
                            <i data-lucide="external-link" class="w-3.5 h-3.5"></i>
                        </button>
                    </div>

                    <!-- 今日の目標・イベント -->
                    <div class="space-y-1">
                        <input type="text" value="${escapeHtml(appData.dailyGoals[dayKey] || '')}" 
                            onchange="appData.dailyGoals['${dayKey}'] = this.value; saveAllData(true);" 
                            placeholder="🎯 今日の目標・イベント名..." 
                            class="w-full bg-slate-50 border border-slate-200 rounded-md p-1.5 text-[10px] font-bold text-slate-700 focus:outline-none focus:bg-white focus:ring-1 focus:ring-indigo-400">
                    </div>

                    <!-- 曜日別TODOリスト -->
                    <div class="space-y-1.5 bg-slate-50/60 p-2 rounded-lg border border-slate-100">
                        <div class="flex justify-between items-center text-[10px] text-slate-400 font-black">
                            <span>SUBJECT / TO DO</span>
                            <button onclick="addDailyToDo('${dayKey}')" class="text-indigo-600 hover:underline flex items-center gap-0.5">
                                <i data-lucide="plus" class="w-2.5 h-2.5"></i>追加
                            </button>
                        </div>
                        <div id="weeklyDailyToDoContainer-${dayKey}" class="space-y-1 max-h-24 overflow-y-auto pr-0.5">
                            <!-- JSでToDoを描画 -->
                        </div>
                    </div>

                    <!-- 縦型ミニバーチカル (6:00 〜 24:00 まで30分単位 of 36マス) -->
                    <div class="space-y-1 border border-slate-150 rounded-lg p-1.5 bg-slate-50">
                        <div class="grid grid-cols-12 text-[8px] font-black text-slate-400 text-center select-none border-b pb-1 mb-1">
                            <div class="col-span-3">時間</div>
                            <div class="col-span-4 text-indigo-500">P</div>
                            <div class="col-span-5 text-emerald-600">A</div>
                        </div>
                        <!-- 縦にぎゅっと並んだミニスクロール -->
                        <div class="space-y-0.5 max-h-36 overflow-y-auto pr-0.5">
                            ${renderMiniVerticalTimeBlocks(dayKey, dayData)}
                        </div>
                    </div>

                    <!-- 曜日TOTAL & メモ -->
                    <div class="pt-1.5 border-t border-slate-100 flex items-center justify-between text-[10px]">
                        <span class="text-emerald-700 font-bold bg-emerald-50 px-2 py-0.5 rounded border border-emerald-100">${totalStr}</span>
                        <input type="text" value="${escapeHtml(progressObj['__memo'] || '')}" 
                            onchange="updateMonthlyCell(${dayD}, '__memo', this.value); renderWeeklyView();" 
                            placeholder="一言メモ..." 
                            class="bg-transparent text-right text-slate-500 focus:outline-none focus:bg-white px-1.5 py-0.5 border border-transparent focus:border-slate-200 rounded max-w-[100px]">
                    </div>
                `;

                if (idx < 3) {
                    leftContainer.appendChild(card);
                } else {
                    rightContainer.appendChild(card);
                }

                // 各曜日ToDoリストの描画
                renderDailyToDoList(dayKey);
            });

            // 今週の総学習時間の更新
            const weekHrs = Math.floor(weekTotalMins / 60);
            const weekMins = weekTotalMins % 60;
            document.getElementById('weeklyTotalTimeLabel').innerText = `${weekHrs}h ${weekMins.toString().padStart(2, '0')}m`;

            renderBrushPalette();
            safeCreateIcons();
        }

        // --- ウィークリーバーチカル内の極小予定・実績マスの生成 ---
        function renderMiniVerticalTimeBlocks(dayKey, dayData) {
            let html = '';
            // 6:00 から 23:30 までの36セル
            for (let j = 0; j < 36; j++) {
                const globalIdx = j + 12; // 6:00はインデックス12
                const hr = Math.floor(globalIdx / 2);
                const min = globalIdx % 2 === 0 ? "00" : "30";
                const timeStr = `${hr.toString().padStart(2, '0')}:${min}`;

                // 2時間に1回だけ時間文字を表示
                const timeLabel = min === "00" && hr % 2 === 0 ? `${hr}h` : "";

                const pSub = dayData.plans[globalIdx];
                const aSub = dayData.actuals[globalIdx];

                let pBg = "bg-slate-100 hover:bg-indigo-50 border border-slate-200/50";
                if (pSub) {
                    const c = colorPalette[appData.subjectColors[pSub] || 'indigo'];
                    pBg = `${c.bg} opacity-60 border-none`;
                }

                let aBg = "bg-slate-100 hover:bg-emerald-50 border border-slate-200/50";
                if (aSub) {
                    const c = colorPalette[appData.subjectColors[aSub] || 'indigo'];
                    aBg = `${c.bg} border-none shadow-sm`;
                }

                html += `
                    <div class="grid grid-cols-12 gap-1 items-center">
                        <span class="col-span-3 text-[8px] font-mono font-bold text-slate-400 select-none text-right pr-1">${timeLabel}</span>
                        <!-- 予定セル -->
                        <button onclick="paintWeeklyCell('${dayKey}', ${globalIdx}, 'plan')" title="${timeStr} 予定: ${pSub || '未設定'}" class="col-span-4 h-3 rounded ${pBg} focus:outline-none"></button>
                        <!-- 実績セル -->
                        <button onclick="paintWeeklyCell('${dayKey}', ${globalIdx}, 'actual')" title="${timeStr} 実績: ${aSub || '未設定'}" class="col-span-5 h-3 rounded ${aBg} focus:outline-none"></button>
                    </div>
                `;
            }
            return html;
        }

        function paintWeeklyCell(dayKey, globalIdx, type) {
            const dayData = getOrInitDayTimeline(dayKey);
            if (type === 'plan') {
                if (selectedBrush === 'eraser') {
                    dayData.plans[globalIdx] = null;
                } else if (selectedBrush) {
                    dayData.plans[globalIdx] = selectedBrush;
                }
            } else {
                if (selectedBrush === 'eraser') {
                    dayData.actuals[globalIdx] = null;
                } else if (selectedBrush) {
                    dayData.actuals[globalIdx] = selectedBrush;
                }
            }
            renderWeeklyView();
            saveAllData(true);
        }

        // --- 週間全体ToDoリストの追加・削除・チェックトグル ---
        function addWeeklyToDo() {
            if (!appData.weeklyToDos[currentWeekKey]) appData.weeklyToDos[currentWeekKey] = [];
            appData.weeklyToDos[currentWeekKey].push({
                id: Date.now() + Math.random().toString(36).substr(2, 5),
                text: "今週の勉強ToDo...",
                checked: false
            });
            renderWeeklyToDoList();
            saveAllData(true);
        }

        function renderWeeklyToDoList() {
            const container = document.getElementById('weeklyToDoContainer');
            if (!container) return;
            container.innerHTML = '';

            const list = appData.weeklyToDos[currentWeekKey] || [];
            if (list.length === 0) {
                container.innerHTML = `<p class="text-[10px] text-slate-400 p-2 italic text-center">今週の全体タスクはありません</p>`;
                return;
            }

            list.forEach((item, index) => {
                const div = document.createElement('div');
                div.className = "flex items-center gap-2 justify-between group";
                div.innerHTML = `
                    <div class="flex items-center gap-1.5 min-w-0 flex-grow">
                        <input type="checkbox" ${item.checked ? 'checked' : ''} onchange="toggleWeeklyToDo('${item.id}')" class="w-3.5 h-3.5 rounded text-indigo-600 focus:ring-indigo-500 border-slate-300">
                        <input type="text" value="${escapeHtml(item.text)}" onchange="editWeeklyToDo('${item.id}', this.value)" class="bg-transparent border-b border-transparent focus:border-slate-200 focus:bg-white text-[11px] font-bold text-slate-700 w-full focus:outline-none py-0.5 ${item.checked ? 'line-through text-slate-400 font-normal' : ''}">
                    </div>
                    <button onclick="deleteWeeklyToDo('${item.id}')" class="opacity-0 group-hover:opacity-100 hover:text-rose-600 p-0.5 rounded transition">
                        <i data-lucide="x" class="w-3.5 h-3.5 text-slate-400"></i>
                    </button>
                `;
                container.appendChild(div);
            });
            safeCreateIcons();
        }

        function toggleWeeklyToDo(id) {
            const list = appData.weeklyToDos[currentWeekKey] || [];
            const item = list.find(i => i.id === id);
            if (item) {
                item.checked = !item.checked;
                renderWeeklyToDoList();
                saveAllData(true);
            }
        }

        function editWeeklyToDo(id, val) {
            const list = appData.weeklyToDos[currentWeekKey] || [];
            const item = list.find(i => i.id === id);
            if (item) {
                item.text = val;
                saveAllData(true);
            }
        }

        // --- 曜日別ToDoリストの追加・削除・チェックトグル ---
        function addDailyToDo(dayKey) {
            if (!appData.dailyToDos[dayKey]) appData.dailyToDos[dayKey] = [];
            appData.dailyToDos[dayKey].push({
                id: Date.now() + Math.random().toString(36).substr(2, 5),
                text: "ワークを解く...",
                checked: false
            });
            renderDailyToDoList(dayKey);
            saveAllData(true);
        }

        function renderDailyToDoList(dayKey) {
            const container = document.getElementById(`weeklyDailyToDoContainer-${dayKey}`);
            if (!container) return;
            container.innerHTML = '';

            const list = appData.dailyToDos[dayKey] || [];
            list.forEach(item => {
                const div = document.createElement('div');
                div.className = "flex items-center gap-1.5 justify-between group";
                div.innerHTML = `
                    <div class="flex items-center gap-1 min-w-0 flex-grow">
                        <input type="checkbox" ${item.checked ? 'checked' : ''} onchange="toggleDailyToDo('${dayKey}', '${item.id}')" class="w-3 h-3 rounded text-indigo-500 border-slate-300">
                        <input type="text" value="${escapeHtml(item.text)}" onchange="editDailyToDo('${dayKey}', '${item.id}', this.value)" class="bg-transparent text-[10px] text-slate-700 w-full focus:outline-none focus:bg-white focus:ring-1 focus:ring-indigo-300 rounded px-1 ${item.checked ? 'line-through text-slate-400 font-normal' : 'font-bold'}">
                    </div>
                    <button onclick="deleteDailyToDo('${dayKey}', '${item.id}')" class="opacity-0 group-hover:opacity-100 hover:text-rose-600 transition p-0.5">
                        <i data-lucide="trash" class="w-3 h-3 text-slate-400"></i>
                    </button>
                `;
                container.appendChild(div);
            });
            safeCreateIcons();
        }

        function toggleDailyToDo(dayKey, id) {
            const list = appData.dailyToDos[dayKey] || [];
            const item = list.find(i => i.id === id);
            if (item) {
                item.checked = !item.checked;
                renderDailyToDoList(dayKey);
                saveAllData(true);
            }
        }

        function editDailyToDo(dayKey, id, val) {
            const list = appData.dailyToDos[dayKey] || [];
            const item = list.find(i => i.id === id);
            if (item) {
                item.text = val;
                saveAllData(true);
            }
        }

        function deleteDailyToDo(dayKey, id) {
            if (appData.dailyToDos[dayKey]) {
                appData.dailyToDos[dayKey] = appData.dailyToDos[dayKey].filter(i => i.id !== id);
                renderDailyToDoList(dayKey);
                saveAllData(true);
            }
        }

        function navigateWeeklyWeek(dir) {
            const date = new Date(currentYear, currentMonth - 1, currentSelectedDay);
            date.setDate(date.getDate() + (dir * 7));
            currentYear = date.getFullYear();
            currentMonth = date.getMonth() + 1;
            currentSelectedDay = date.getDate();

            updateGlobalMonthUI();
            renderWeeklyView();
        }

        function deleteWeeklyToDo(id) {
            if (appData.weeklyToDos[currentWeekKey]) {
                appData.weeklyToDos[currentWeekKey] = appData.weeklyToDos[currentWeekKey].filter(i => i.id !== id);
                renderWeeklyToDoList();
                saveAllData(true);
            }
        }

        // --- タイマー処理 & 状態制御 ---
        function setTimerStateMode(mode) {
            timerStateMode = mode;
            const focusBtn = document.getElementById('timerModeFocusBtn');
            const breakBtn = document.getElementById('timerModeBreakBtn');
            const titleLabel = document.getElementById('timerSlotsTitleLabel');
            
            if (mode === 'focus') {
                if (focusBtn) focusBtn.className = "flex-grow py-2 text-xs font-black rounded-lg bg-indigo-600 text-white shadow-sm transition-all";
                if (breakBtn) breakBtn.className = "flex-grow py-2 text-xs font-bold rounded-lg text-slate-600 hover:text-slate-800 transition-all";
                document.getElementById('bigTimerTitle').innerText = "READY TO STUDY";
                document.getElementById('bigTimerTitle').className = "block text-[10px] font-black text-indigo-400 uppercase tracking-wider";
                if (titleLabel) titleLabel.innerHTML = `<i data-lucide="star" class="w-3.5 h-3.5 text-amber-400 fill-amber-400"></i> マイタイマー (集中 5枠)`;
            } else {
                if (breakBtn) breakBtn.className = "flex-grow py-2 text-xs font-black rounded-lg bg-emerald-600 text-white shadow-sm transition-all";
                if (focusBtn) focusBtn.className = "flex-grow py-2 text-xs font-bold rounded-lg text-slate-600 hover:text-slate-800 transition-all";
                document.getElementById('bigTimerTitle').innerText = "TIME TO RELAX";
                document.getElementById('bigTimerTitle').className = "block text-[10px] font-black text-emerald-400 uppercase tracking-wider";
                if (titleLabel) titleLabel.innerHTML = `<i data-lucide="star" class="w-3.5 h-3.5 text-emerald-400 fill-emerald-400"></i> マイタイマー (休憩 5枠)`;
            }
            
            renderTimerPresets();
            const defaultMins = (mode === 'focus') ? 25 : 5;
            setTimerDuration(defaultMins); 
        }

        function selectPomodoroCycle(type) {
            if (type === 'focus') {
                timerStateMode = 'focus';
                const focusBtn = document.getElementById('timerModeFocusBtn');
                const breakBtn = document.getElementById('timerModeBreakBtn');
                if (focusBtn) focusBtn.className = "flex-grow py-2 text-xs font-black rounded-lg bg-indigo-600 text-white shadow-sm transition-all";
                if (breakBtn) breakBtn.className = "flex-grow py-2 text-xs font-bold rounded-lg text-slate-600 hover:text-slate-800 transition-all";
                document.getElementById('bigTimerTitle').innerText = "POMODORO FOCUS";
                document.getElementById('bigTimerTitle').className = "block text-[10px] font-black text-indigo-400 uppercase tracking-wider";
                setTimerDuration(25);
            } else {
                timerStateMode = 'break';
                const focusBtn = document.getElementById('timerModeFocusBtn');
                const breakBtn = document.getElementById('timerModeBreakBtn');
                if (breakBtn) breakBtn.className = "flex-grow py-2 text-xs font-black rounded-lg bg-emerald-600 text-white shadow-sm transition-all";
                if (focusBtn) focusBtn.className = "flex-grow py-2 text-xs font-bold rounded-lg text-slate-600 hover:text-slate-800 transition-all";
                document.getElementById('bigTimerTitle').innerText = "POMODORO BREAK";
                document.getElementById('bigTimerTitle').className = "block text-[10px] font-black text-emerald-400 uppercase tracking-wider";
                setTimerDuration(5);
            }
        }

        function setTimerDuration(mins) {
            if (timerIsRunning) {
                openCustomConfirm({
                    title: 'タイマーのリセット',
                    message: 'タイマー作動中ですが時間を変更しますか？現在のタイマーはリセットされます。',
                    icon: 'alert-triangle',
                    colorClass: 'amber',
                    okText: '変更する',
                    onConfirm: () => {
                        stopGlobalTimerInterval();
                        stopAlarmLoop();
                        timerIsOvertime = false;
                        timerOvertimeSeconds = 0;
                        timerSecondsTotal = mins * 60;
                        timerSecondsLeft = timerSecondsTotal;
                        updateTimerDisplay();
                        renderTimerPresets();
                    }
                });
            } else {
                stopAlarmLoop();
                timerIsOvertime = false;
                timerOvertimeSeconds = 0;
                timerSecondsTotal = mins * 60;
                timerSecondsLeft = timerSecondsTotal;
                updateTimerDisplay();
                renderTimerPresets();
            }
        }

        // --- マイタイマーの管理 (集中5枠＋休憩5枠) ---
        function renderTimerPresets() {
            const container = document.getElementById('customTimerSlotsContainer');
            if (!container) return;
            container.innerHTML = '';

            const activeSlots = (timerStateMode === 'focus') ? appData.timerSlotsFocus : appData.timerSlotsBreak;

            activeSlots.forEach((slot, index) => {
                const isSelected = (timerSecondsTotal === slot.mins * 60);
                const isEditing = (editingTimerSlotIndex === index);

                const card = document.createElement('div');
                card.className = `p-3 rounded-xl border transition-all ${
                    isSelected 
                    ? (timerStateMode === 'focus' ? 'bg-indigo-50/80 border-indigo-300 shadow-sm' : 'bg-emerald-50/80 border-emerald-300 shadow-sm')
                    : 'bg-slate-50 hover:bg-slate-100/50 border-slate-200'
                }`;

                if (isEditing) {
                    card.innerHTML = `
                        <div class="space-y-2">
                            <div>
                                <label class="block text-[9px] font-black text-slate-400 mb-1">タイマー名</label>
                                <input type="text" id="editSlotLabel-${index}" value="${escapeHtml(slot.label)}" class="w-full bg-white border border-slate-200 rounded-lg p-1.5 text-xs font-bold focus:outline-none focus:ring-1 focus:ring-indigo-500 text-slate-700">
                            </div>
                            <div>
                                <label class="block text-[9px] font-black text-slate-400 mb-1">時間 (分)</label>
                                <input type="number" id="editSlotMins-${index}" value="${slot.mins}" min="1" max="999" class="w-full bg-white border border-slate-200 rounded-lg p-1.5 text-xs font-mono font-bold focus:outline-none focus:ring-1 focus:ring-indigo-500 text-slate-700">
                            </div>
                            <div class="flex justify-end gap-1.5 pt-1">
                                <button onclick="cancelEditingTimerSlot()" class="px-2.5 py-1 text-[10px] bg-slate-200 text-slate-600 rounded-lg font-bold">戻る</button>
                                <button onclick="saveTimerSlot(${index})" class="px-2.5 py-1 text-[10px] bg-indigo-600 text-white rounded-lg font-bold">適用</button>
                            </div>
                        </div>
                    `;
                } else {
                    const modeBadge = (timerStateMode === 'focus') 
                        ? `<span class="bg-indigo-100 text-indigo-700 text-[8px] font-black px-1.5 py-0.5 rounded-full shrink-0">集中</span>` 
                        : `<span class="bg-emerald-100 text-emerald-700 text-[8px] font-black px-1.5 py-0.5 rounded-full shrink-0">休憩</span>`;

                    card.innerHTML = `
                        <div class="flex items-center justify-between gap-2">
                            <div onclick="applyTimerSlot(${index})" class="flex-grow flex items-center justify-between min-w-0 cursor-pointer">
                                <div class="flex items-center gap-2 min-w-0">
                                    ${modeBadge}
                                    <span class="font-bold text-xs text-slate-700 truncate">${escapeHtml(slot.label)}</span>
                                </div>
                                <span class="font-mono bg-white px-2 py-0.5 rounded border text-[10px] font-bold text-slate-600 shrink-0">${slot.mins}分</span>
                            </div>
                            <button onclick="startEditingTimerSlot(${index}, event)" class="p-1.5 hover:bg-slate-200 text-slate-400 hover:text-slate-700 rounded transition shrink-0" title="このタイマーの設定を変更">
                                <i data-lucide="edit-3" class="w-3.5 h-3.5"></i>
                            </button>
                        </div>
                    `;
                }
                container.appendChild(card);
            });
            updateTimerSummaryLabel();
            safeCreateIcons();
        }

        function startEditingTimerSlot(index, e) {
            e.stopPropagation();
            editingTimerSlotIndex = index;
            renderTimerPresets();
        }

        function cancelEditingTimerSlot() {
            editingTimerSlotIndex = null;
            renderTimerPresets();
        }

        function saveTimerSlot(index) {
            const labelInput = document.getElementById(`editSlotLabel-${index}`);
            const minsInput = document.getElementById(`editSlotMins-${index}`);

            if (!labelInput || !minsInput) return;

            const label = labelInput.value.trim();
            const mins = parseInt(minsInput.value);

            if (!label) {
                alert("タイマー名を入力してください。");
                return;
            }
            if (isNaN(mins) || mins <= 0) {
                alert("正しい時間を入力してください。");
                return;
            }

            if (timerStateMode === 'focus') {
                appData.timerSlotsFocus[index] = { label, mins };
            } else {
                appData.timerSlotsBreak[index] = { label, mins };
            }

            editingTimerSlotIndex = null;

            saveAllData(); 
            renderTimerPresets();
            applyTimerSlot(index);
        }

        function applyTimerSlot(index) {
            const activeSlots = (timerStateMode === 'focus') ? appData.timerSlotsFocus : appData.timerSlotsBreak;
            const slot = activeSlots[index];
            if (!slot) return;
            
            const matchedSub = subjects.find(s => s.toLowerCase() === slot.label.toLowerCase());
            if (matchedSub && timerStateMode === 'focus') {
                timerSubjectSelected = matchedSub;
                renderTimerClassifications();
            }

            setTimerDuration(slot.mins);
        }

        function renderTimerClassifications() {
            const container = document.getElementById('classificationListContainer');
            if (!container) return;
            container.innerHTML = '';
            
            if (subjects.length === 0) {
                container.innerHTML = `<p class="text-[10px] text-slate-400 p-2">登録教科がありません</p>`;
                return;
            }

            subjects.forEach(sub => {
                const isSelected = (timerSubjectSelected === sub);
                const c = colorPalette[appData.subjectColors[sub] || 'indigo'];
                const btn = document.createElement('button');
                btn.className = `w-full text-left p-2 rounded-lg text-xs flex items-center gap-2 transition-all ${isSelected ? 'bg-slate-100 border border-slate-300 font-bold text-slate-800' : 'hover:bg-slate-50 text-slate-600'}`;
                btn.innerHTML = `
                    <span class="w-2.5 h-2.5 rounded-full ${c.bg}"></span>
                    <span class="truncate">${sub}</span>
                    ${isSelected ? `<i data-lucide="check" class="w-3.5 h-3.5 ml-auto text-slate-500"></i>` : ''}
                `;
                btn.onclick = () => {
                    timerSubjectSelected = sub;
                    renderTimerClassifications();
                    updateTimerSummaryLabel();
                    saveAllData(true); 
                };
                container.appendChild(btn);
            });
            safeCreateIcons();
        }

        function updateTimerSummaryLabel() {
            const mins = Math.round(timerSecondsTotal / 60);
            const mLabel = timerStateMode === 'focus' ? '集中' : '休憩';
            const lblMode = document.getElementById('summaryModeLabel');
            if (lblMode) {
                lblMode.innerText = `${mLabel} [${mins}分]`;
                if (timerStateMode === 'focus') {
                    lblMode.className = "text-indigo-600";
                } else {
                    lblMode.className = "text-emerald-600";
                }
            }
            const lblSubject = document.getElementById('summarySubjectLabel');
            if (lblSubject) {
                lblSubject.innerText = timerStateMode === 'focus' ? timerSubjectSelected : '（休憩中）';
            }
        }

        function updateTimerDisplay() {
            const displayOverlay = document.getElementById('fullscreenTimerOverlay');
            const isOverlayVisible = displayOverlay && !displayOverlay.classList.contains('hidden');

            if (timerIsOvertime) {
                const m = Math.floor(timerOvertimeSeconds / 60).toString().padStart(2, '0');
                const s = (timerOvertimeSeconds % 60).toString().padStart(2, '0');
                const str = `+${m}:${s}`;
                
                const bigTimerDisplay = document.getElementById('bigTimerDisplay');
                if (bigTimerDisplay) {
                    bigTimerDisplay.innerText = str;
                    bigTimerDisplay.className = "font-mono text-5xl sm:text-6xl font-black tracking-widest text-rose-500 select-none block animate-pulse";
                }
                
                const fullscreenDigits = document.getElementById('fullscreenDigits');
                if (fullscreenDigits) {
                    fullscreenDigits.innerText = str;
                    fullscreenDigits.className = "font-mono text-5xl sm:text-6xl font-black text-rose-500 tracking-widest block";
                }

                const percentageText = document.getElementById('fullscreenPercentage');
                if (percentageText) {
                    percentageText.innerText = "OVERTIME RECORDING...";
                    percentageText.className = "text-[10px] font-black text-rose-500 block animate-pulse";
                }

                document.getElementById('mainTimerOvertimeLabel').classList.remove('hidden');

                const ring = document.getElementById('fullscreenProgressRing');
                if (ring) {
                    ring.className = "stroke-rose-500 transition-all duration-300";
                    ring.style.strokeDashoffset = 0;
                }
            } else {
                const m = Math.floor(timerSecondsLeft / 60).toString().padStart(2, '0');
                const s = (timerSecondsLeft % 60).toString().padStart(2, '0');
                const str = `${m}:${s}`;
                
                const bigTimerDisplay = document.getElementById('bigTimerDisplay');
                if (bigTimerDisplay) {
                    bigTimerDisplay.innerText = str;
                    bigTimerDisplay.className = "font-mono text-5xl sm:text-6xl font-black tracking-widest text-slate-100 select-none block";
                }
                
                const fullscreenDigits = document.getElementById('fullscreenDigits');
                if (fullscreenDigits) {
                    fullscreenDigits.innerText = str;
                    fullscreenDigits.className = "font-mono text-5xl sm:text-6xl font-black text-slate-100 tracking-widest block";
                }

                document.getElementById('mainTimerOvertimeLabel').classList.add('hidden');

                const ring = document.getElementById('fullscreenProgressRing');
                const percent = timerSecondsTotal > 0 ? (timerSecondsLeft / timerSecondsTotal) : 0;
                const offset = 1000 - (1000 * percent);
                if (ring) {
                    ring.style.strokeDashoffset = offset;
                    if (timerStateMode === 'focus') {
                        ring.className = "stroke-indigo-500 transition-all duration-300";
                    } else {
                        ring.className = "stroke-emerald-500 transition-all duration-300";
                    }
                }
                
                const percentageText = document.getElementById('fullscreenPercentage');
                if (percentageText) {
                    percentageText.innerText = `${Math.ceil(percent * 100)}% REMAINING`;
                    percentageText.className = "text-[10px] font-black text-slate-500 block";
                }
            }
        }

        // --- 音声生成 (Beep) ---
        function startAlarmLoop() {
            if (alarmIntervalId) return;
            if (!audioCtx) {
                audioCtx = new (window.AudioContext || window.webkitAudioContext)();
            }
            const playTone = () => {
                try {
                    if (audioCtx.state === 'suspended') {
                        audioCtx.resume();
                    }
                    const osc = audioCtx.createOscillator();
                    const gain = audioCtx.createGain();
                    osc.type = 'sine';
                    osc.frequency.setValueAtTime(659.25, audioCtx.currentTime); // E5
                    osc.frequency.setValueAtTime(523.25, audioCtx.currentTime + 0.15); // C5
                    
                    gain.gain.setValueAtTime(0.25, audioCtx.currentTime);
                    gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.49);
                    
                    osc.connect(gain);
                    gain.connect(audioCtx.destination);
                    osc.start();
                    osc.stop(audioCtx.currentTime + 0.5);
                } catch (e) {
                    console.error("Synthesizer audio fail:", e);
                }
            };
            playTone();
            alarmIntervalId = setInterval(playTone, 1000);
        }

        function stopAlarmLoop() {
            if (alarmIntervalId) {
                clearInterval(alarmIntervalId);
                alarmIntervalId = null;
            }
        }

        function stopGlobalTimerInterval() {
            if (timerIntervalId) {
                clearInterval(timerIntervalId);
                timerIntervalId = null;
            }
            timerIsRunning = false;
        }

        // --- フルスクリーンタイマー制御 ---
        function startFullscreenTimer() {
            document.getElementById('fullscreenTimerOverlay').classList.remove('hidden');
            
            const labelEl = document.getElementById('fullscreenSubjectLabel');
            
            if (!timerIsOvertime) {
                if (timerStateMode === 'focus') {
                    if (labelEl) {
                        labelEl.innerText = `${timerSubjectSelected} 集中時間`;
                        labelEl.className = "text-xs font-black text-indigo-400 tracking-wider";
                    }
                    const msg = document.getElementById('fullscreenInspiringMessage');
                    if (msg) msg.innerText = "スマートフォンを裏返して、自分だけの特別な勉強時間に集中しましょう。";
                } else {
                    if (labelEl) {
                        labelEl.innerText = `リフレッシュ休憩時間`;
                        labelEl.className = "text-xs font-black text-emerald-400 tracking-wider";
                    }
                    const msg = document.getElementById('fullscreenInspiringMessage');
                    if (msg) msg.innerText = "しっかり脳を休めましょう。お疲れ様でした！";
                }
            } else {
                if (labelEl) {
                    labelEl.innerText = "【超記録中】" + (timerStateMode === 'focus' ? timerSubjectSelected : '休憩');
                    labelEl.className = "text-xs font-black text-rose-500 tracking-wider";
                }
            }

            timerIsRunning = true;
            updatePlayPauseIconUI();
            
            if (!timerIntervalId) {
                timerIntervalId = setInterval(() => {
                    if (timerSecondsLeft > 0) {
                        timerSecondsLeft--;
                        updateTimerDisplay();
                    } else {
                        if (!timerIsOvertime) {
                            timerIsOvertime = true;
                            timerOvertimeSeconds = 0;
                            startAlarmLoop();
                        }
                        timerOvertimeSeconds++;
                        updateTimerDisplay();
                    }
                }, 1000);
            }
            updateTimerDisplay();
        }

        function toggleFullscreenTimer() {
            if (timerIsRunning) {
                timerIsRunning = false;
                if (timerIntervalId) {
                    clearInterval(timerIntervalId);
                    timerIntervalId = null;
                }
                stopAlarmLoop(); 
            } else {
                timerIsRunning = true;
                if (timerIsOvertime) {
                    startAlarmLoop(); 
                }
                timerIntervalId = setInterval(() => {
                    if (timerSecondsLeft > 0) {
                        timerSecondsLeft--;
                        updateTimerDisplay();
                    } else {
                        if (!timerIsOvertime) {
                            timerIsOvertime = true;
                            timerOvertimeSeconds = 0;
                            startAlarmLoop();
                        }
                        timerOvertimeSeconds++;
                        updateTimerDisplay();
                    }
                }, 1000);
            }
            updatePlayPauseIconUI();
        }

        function updatePlayPauseIconUI() {
            const icon = document.getElementById('fullscreenPlayIcon');
            if (icon) {
                if (timerIsRunning) {
                    icon.setAttribute('data-lucide', 'pause');
                } else {
                    icon.setAttribute('data-lucide', 'play');
                }
            }
            safeCreateIcons();
        }

        function resetFullscreenTimer() {
            openCustomConfirm({
                title: 'タイマーのやり直し',
                message: '最初からタイマーをやり直しますか？現在の超過記録などはリセットされます。',
                icon: 'rotate-ccw',
                colorClass: 'indigo',
                okText: 'やり直す',
                onConfirm: () => {
                    stopAlarmLoop();
                    timerIsOvertime = false;
                    timerOvertimeSeconds = 0;
                    timerSecondsLeft = timerSecondsTotal;
                    updateTimerDisplay();
                }
            });
        }

        function quitFullscreenTimerConfirm() {
            openCustomConfirm({
                title: 'タイマーの中断',
                message: 'タイマーを中断して元の画面に戻りますか？今回の学習実績は記録されません。',
                icon: 'alert-circle',
                colorClass: 'rose',
                okText: '中断する',
                onConfirm: () => {
                    stopGlobalTimerInterval();
                    stopAlarmLoop();
                    timerIsOvertime = false;
                    timerOvertimeSeconds = 0;
                    document.getElementById('fullscreenTimerOverlay').classList.add('hidden');
                    updateTimerDisplay();
                }
            });
        }

        function forceCompleteTimerConfirm() {
            let passedMins = 0;
            if (timerIsOvertime) {
                passedMins = Math.floor((timerSecondsTotal + timerOvertimeSeconds) / 60);
            } else {
                passedMins = Math.floor((timerSecondsTotal - timerSecondsLeft) / 60);
            }

            openCustomConfirm({
                title: '実績の完了・記録',
                message: `タイマーを終了し、経過した合計時間（${passedMins}分）を今日の学習実績として登録しますか？`,
                icon: 'check-circle-2',
                colorClass: 'emerald',
                okText: '実績を登録して終了',
                onConfirm: () => {
                    stopGlobalTimerInterval();
                    stopAlarmLoop();
                    
                    document.getElementById('fullscreenTimerOverlay').classList.add('hidden');
                    
                    if (timerStateMode === 'focus' && passedMins > 0) {
                        injectMinutesToDailyGrid(timerSubjectSelected, passedMins);
                    } else {
                        showToast("⏱️ タイマーを終了しました。");
                    }
                    
                    const completedMode = timerStateMode; 
                    
                    timerIsOvertime = false;
                    timerOvertimeSeconds = 0;
                    timerSecondsLeft = timerSecondsTotal;
                    updateTimerDisplay();

                    if (appData.pomodoroAutoLoop) {
                        setTimeout(() => {
                            if (completedMode === 'focus') {
                                showToast("🔄 集中完了！自動的に5分の休憩ポモドーロを開始します。");
                                selectPomodoroCycle('break');
                            } else {
                                showToast("🔄 休憩終了！自動的に25分の集中ポモドーロを開始します。");
                                selectPomodoroCycle('focus');
                            }
                            startFullscreenTimer();
                        }, 800);
                    }
                }
            });
        }

        // --- 記録枠への時間の割り当て ---
        function injectMinutesToDailyGrid(subName, mins) {
            const dayKey = `${currentYear}-${currentMonth}-${currentSelectedDay}`;
            const dayData = getOrInitDayTimeline(dayKey);
            
            let cellsNeeded = Math.ceil(mins / 30);
            let actuals = dayData.actuals;
            
            let injectedCount = 0;
            for (let i = 18; i < 48; i++) { // 午前9時以降の空き枠を探す
                if (actuals[i] === null) {
                    actuals[i] = subName;
                    injectedCount++;
                    if (injectedCount >= cellsNeeded) break;
                }
            }
            if (injectedCount < cellsNeeded) {
                for (let i = 0; i < 18; i++) {
                    if (actuals[i] === null) {
                        actuals[i] = subName;
                        injectedCount++;
                        if (injectedCount >= cellsNeeded) break;
                    }
                }
            }
            
            if (!appData.monthlyProgress[dayKey]) appData.monthlyProgress[dayKey] = {};
            if (!appData.monthlyProgress[dayKey][subName]) {
                appData.monthlyProgress[dayKey][subName] = `タイマー学習計 ${mins}分`;
            }
            
            initApp();
            saveAllData(); 
        }

        // --- Chart.js 制御 ---
        function initCharts() {
            const pieCanvas = document.getElementById('subjectPieChart');
            if (pieCanvas) {
                const ctxPie = pieCanvas.getContext('2d');
                if (pieChartInstance) {
                    pieChartInstance.destroy();
                }
                pieChartInstance = new Chart(ctxPie, {
                    type: 'doughnut',
                    data: { labels: [], datasets: [{ data: [], backgroundColor: [] }] },
                    options: {
                        responsive: true,
                        maintainAspectRatio: false,
                        plugins: { legend: { position: 'bottom', labels: { boxWidth: 12, font: { size: 10 } } } }
                    }
                });
            }

            const trendCanvas = document.getElementById('dailyTrendChart');
            if (trendCanvas) {
                const ctxTrend = trendCanvas.getContext('2d');
                if (trendChartInstance) {
                    trendChartInstance.destroy();
                }
                trendChartInstance = new Chart(ctxTrend, {
                    type: 'bar',
                    data: { labels: [], datasets: [] },
                    options: {
                        responsive: true,
                        maintainAspectRatio: false,
                        scales: {
                            x: { grid: { display: false }, ticks: { font: { size: 9 } } },
                            y: { beginAtZero: true, ticks: { font: { size: 9 } } },
                        },
                        plugins: { legend: { display: true, position: 'top', labels: { boxWidth: 10, font: { size: 10 } } } }
                    }
                });
            }
            updateCharts();
        }

        function setTrendViewMode(mode) {
            trendViewMode = mode;
            document.getElementById('trendModeWeek').className = mode === 'week' ? "px-3 py-1.5 text-xs font-bold rounded-lg bg-white text-slate-800 shadow-sm transition-all" : "px-3 py-1.5 text-xs font-bold rounded-lg text-slate-500 hover:text-slate-700 transition-all";
            document.getElementById('trendModeMonth').className = mode === 'month' ? "px-3 py-1.5 text-xs font-bold rounded-lg bg-white text-slate-800 shadow-sm transition-all" : "px-3 py-1.5 text-xs font-bold rounded-lg text-slate-500 hover:text-slate-700 transition-all";
            document.getElementById('trendModeYear').className = mode === 'year' ? "px-3 py-1.5 text-xs font-bold rounded-lg bg-white text-slate-800 shadow-sm transition-all" : "px-3 py-1.5 text-xs font-bold rounded-lg text-slate-500 hover:text-slate-700 transition-all";
            updateCharts();
        }

        function updateCharts() {
            if (!pieChartInstance || !trendChartInstance) return;

            const daysCount = getDaysInMonth(currentYear, currentMonth);
            let subjectMinsMap = {};
            subjects.forEach(s => subjectMinsMap[s] = 0);

            // 全期間の中から、選択している年に含まれる全データを教科ごとに集計（円グラフ用）
            for (let d = 1; d <= daysCount; d++) {
                const dayKey = `${currentYear}-${currentMonth}-${d}`;
                const dayData = appData.dailyTimelines[dayKey];
                if (dayData && dayData.actuals) {
                    dayData.actuals.forEach(val => {
                        if (val && subjectMinsMap[val] !== undefined) {
                            subjectMinsMap[val] += 30;
                        }
                    });
                }
            }

            // 円グラフ更新
            let labels = [];
            let data = [];
            let bgColors = [];
            subjects.forEach(sub => {
                labels.push(sub);
                data.push(subjectMinsMap[sub]);
                bgColors.push(colorPalette[appData.subjectColors[sub] || 'indigo'].dot);
            });

            if (data.every(v => v === 0)) {
                labels = ["データなし"];
                data = [1];
                bgColors = ["#e2e8f0"];
            }

            pieChartInstance.data.labels = labels;
            pieChartInstance.data.datasets[0].data = data;
            pieChartInstance.data.datasets[0].backgroundColor = bgColors;
            pieChartInstance.update();

            // 推移グラフ更新
            if (trendViewMode === 'month') {
                // 1. 月別表示（日ごと）
                let xLabels = [];
                let datasetsMap = {};
                subjects.forEach(sub => {
                    datasetsMap[sub] = Array(daysCount).fill(0);
                });

                for (let d = 1; d <= daysCount; d++) {
                    xLabels.push(`${d}日`);
                    const dayKey = `${currentYear}-${currentMonth}-${d}`;
                    const dayData = appData.dailyTimelines[dayKey];
                    if (dayData && dayData.actuals) {
                        dayData.actuals.forEach(val => {
                            if (val && datasetsMap[val]) {
                                datasetsMap[val][d - 1] += 30;
                            }
                        });
                    }
                }

                trendChartInstance.data.labels = xLabels;
                trendChartInstance.data.datasets = subjects.map(sub => ({
                    label: sub,
                    data: datasetsMap[sub],
                    backgroundColor: colorPalette[appData.subjectColors[sub] || 'indigo'].dot,
                    borderRadius: 4
                }));

            } else if (trendViewMode === 'week') {
                // 2. 週別表示
                let xLabels = [];
                let datasetsMap = {};
                subjects.forEach(sub => datasetsMap[sub] = Array(7).fill(0));

                for (let i = 6; i >= 0; i--) {
                    let targetDate = new Date(currentYear, currentMonth - 1, currentSelectedDay - i);
                    let tY = targetDate.getFullYear();
                    let tM = targetDate.getMonth() + 1;
                    let tD = targetDate.getDate();
                    
                    xLabels.push(`${tM}/${tD}`);
                    const dayKey = `${tY}-${tM}-${tD}`;
                    const dayData = appData.dailyTimelines[dayKey];
                    
                    if (dayData && dayData.actuals) {
                        dayData.actuals.forEach(val => {
                            if (val && datasetsMap[val]) {
                                datasetsMap[val][6 - i] = (datasetsMap[val][6 - i] || 0) + 30;
                            }
                        });
                    }
                }

                trendChartInstance.data.labels = xLabels;
                trendChartInstance.data.datasets = subjects.map(sub => ({
                    label: sub,
                    data: datasetsMap[sub],
                    backgroundColor: colorPalette[appData.subjectColors[sub] || 'indigo'].dot,
                    borderRadius: 4
                }));

            } else if (trendViewMode === 'year') {
                // 3. 年間表示 (1月〜12月の一ヶ月ごとの合計時間)
                let xLabels = ["1月", "2月", "3月", "4月", "5月", "6月", "7月", "8月", "9月", "10月", "11月", "12月"];
                let datasetsMap = {};
                subjects.forEach(sub => {
                    datasetsMap[sub] = Array(12).fill(0); // 12ヶ月分
                });

                // 選択されている年のすべての月の全データを算出
                for (let m = 1; m <= 12; m++) {
                    const daysInM = getDaysInMonth(currentYear, m);
                    for (let d = 1; d <= daysInM; d++) {
                        const dayKey = `${currentYear}-${m}-${d}`;
                        const dayData = appData.dailyTimelines[dayKey];
                        if (dayData && dayData.actuals) {
                            dayData.actuals.forEach(val => {
                                if (val && datasetsMap[val]) {
                                    datasetsMap[val][m - 1] += 30; // 単位を「分」として加算
                                }
                            });
                        }
                    }
                }

                trendChartInstance.data.labels = xLabels;
                trendChartInstance.data.datasets = subjects.map(sub => ({
                    label: sub,
                    data: datasetsMap[sub],
                    backgroundColor: colorPalette[appData.subjectColors[sub] || 'indigo'].dot,
                    borderRadius: 6
                }));
            }
            trendChartInstance.update();
        }

        // --- ユーティリティ ---
        function escapeHtml(str) {
            if (!str) return '';
            return str.replace(/&/g, '&amp;').replace(/</g, '&lt;').replace(/>/g, '&gt;').replace(/"/g, '&quot;').replace(/'/g, '&#039;');
        }
        function escapeJsString(str) {
            if (!str) return '';
            return str.replace(/\\/g, '\\\\').replace(/'/g, "\\'").replace(/"/g, '\\"');
        }
    </script>
</body>
</html>
