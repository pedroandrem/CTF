## Challenge Name: Log Hunt
Category: General Skills
Difficulty: Easy


### Challenge Description
Our server seems to be leaking pieces of a secret flag in its logs. The parts are scattered and sometimes repeated. Can you reconstruct the original flag?
Find the server logs file in `Files/`, named *server.log*, and extract the flag.

---

## Files:
* [Server Logs](Files/server.log)

---

### Approach

### 1. Server Logs Inspection
Initial investigation of the server.log file suggested a flag fragment might be present, particularly within the first 20 lines. To isolate and clean the data across the entire log, I constructed a command pipeline. First, grep was used to extract all relevant log entries containing the flag part. Next, sed was applied to strip the surrounding log structure (timestamp, log level, and prefix), leaving only the raw flag value. Finally, due to numerous duplicate entries, the output was channeled to sort | uniq to yield the complete set of unique flag segments.

```bash 
grep "INFO FLAGPART:" server.log | sed 's/.*INFO FLAGPART: //g' | sort | uniq
Output: cedfa5fb}
picoCTF{us3_
sk1lls_
y0urlinux_
```
### 2. Flag Reconstruction
After obtaining the unique segments (picoCTF{us3_, y0urlinux_, sk1lls_, cedfa5fb}), the final step was concatenation. The correct order was easily inferred due to the known structure of picoCTF flags (starting with picoCTF{ and concluding with the closing bracket).
Piecing everything together in the logical sequence, the final flag is:
```bash
picoCTF{us3_y0urlinux_sk1lls_cedfa5fb}
```

Flag successfully recovered 🎉



### Reflections
This challenge was a practical exercise in effective log file analysis using standard Linux command-line utilities.
- The most crucial takeway was the efficiency of chaining commands together (grep | sed | sort | uniq). This technique allows for a complex data cleanng and filtration in a single, powerful line.
- Using sed was key to data hygiene, as it allowed us to precisely strip the unnecessary log formatting (timestamps and prefixes), leaving only the raw, desired flag values.
- Recognizing and quickly solving the issue of duplicate entries using sort and uniq is essential for dealing with large, verbose log files in a CTF environment.

---
[Back to home](<https://github.com/pedroandrem/CTF/tree/main/picoCTF>)
