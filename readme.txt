for i in {1..100}; do echo "This is a text file $i" > "text_file_$i.txt"; done

for i in {1..100}; do echo "This is an informational data for all employees" >> "text_file_$i.txt"; done

for i in {1..100}; do
  if (( i % 2 == 0 )); then
    echo "Also, in addition, we must have a meeting ASAP" >> "text_file_$i.txt"
  fi
done

for i in {2..100..2}; do sed -i '/Also, in addition, we must have a meeting ASAP/d' "text_file_$i.txt"; done

for i in {2..100..2}; do rm "text_file_$i.txt"; done

counter=1; for file in $(ls -v text_file_*); do mv "$file" "text_file_$counter.txt"; ((counter++)); done
